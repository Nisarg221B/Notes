next:- [[Markov Decision Processes]]

#machine_learning 
#reinforcement_learning 

---

What makes reinforcement learning different from other machine learning paradigm ? 
- There is no supervisor , only a reward signal
- Feedback is delayed , not instantaneous
- Time really matters ( sequential , non i.i.d. data)
- Agent's action affect the subsequent data it receives.

ex : 
1. Fly stunt manoeuvres in a helicopter
2. Manage investment portfolio
3. Defeat the world champion at Backgammon
4. Control a power station - to optimise the throughput of the station.
5. make a humanoid robot walk.
6. Play many different Atari games better than humans.

## Reinforcement Learning Problem

- A reward Rt is a scalar feedback signal.
- Indicates how well agent is doing at step t.
- The agent's job is to maximize cumulative reward.

#reinforcement_learning-reward 
**Definition ( Reward Hypothesis )**
All goals can be described by the maximisation of expected cumulative reward

- Fly stunt manoeuvres in helicopter 
	- +ve reward for following desired trajectory
	- -ve reward for crashing
- Defeat the world champion at backgammon
	- +/-ve reward for winning / losing a game
- Manage an investment portfolio
	- +ve reward for each $ in bank.
- Control a power station
	- +ve reward for producing power
	- -ve reward for exceeding safety thresholds
- Make a humanoid robot walk
	- +ve reward for forward motion
	- -ve reward for falling over.

**GOAL : select actions to maximize total future reward**

1. Actions may have long term consequences 
2. Reward may be delayed
3. it may be better to sacrifice immediate reward to gain more long term reward.
4. Examples :
	- A financial investment ( may take months to mature)
	- Refuelling a helicopter ( might prevent a crash in several hours)
	- Blocking opponent moves(might help winning chances many moves from now)

![[Screenshot 2023-04-20 at 10.31.54 AM.png]]


### History and State

The history is sequence of observations , actions , rewards

Ht = A1, O1 , R1 , ... , At , Ot , Rt

- All observable variables up to time t
- The sensorimotor stream of a robot or embodied agent.
- What happens next depends on this history:
	- The agent selects actions
	- The environment selects observations/rewards
- **State** is the information used to determine what happens next
- Formally state is function of the history : 
	  St =  f(Ht)
        valid definition of state would be to look at only the last observation (note: last 4 observations and ignore the rest - atari)

### Environment State 

![[Screenshot 2023-04-20 at 11.34.26 AM.png]]
### Agent State 

![[Screenshot 2023-04-20 at 11.36.25 AM.png]]

### Information State (Markov state)

An information state contains all useful information from the history.

A state St is Markov if and only if : 
	P[St+1 | St] = P[St+1 | S1,...St]

i.e the probability of getting to state st+1 given that you are in state St is same as probability of getting to state st+1 with sequence of state s1,..st

"The future is independent of the past given the present"
- H 1:t --> St --> H t+1:inf

Once the state is known the history may be thrown away
i.e. the state is a sufficient statistic of the future.

The environment state St(e) is Markov .
The History Ht is Markov also but not very useful.

### Fully observable Environments 

Fully Observability : agent directly observes environment state
			Ot = Sa(t) = Se(t)
		Ot - observations that we see
	Sa(t) - agent state
	Se(t) - environment State

- Agent state = environment state = information state
- Formally , this is a Markov decision process ( MDP )

### Partially observable Environments 

- Partial observability : agent **Indirectly** observes environment.
	- A robot with camera vision isn't told its absolute location it has to figure out on its own where it is in the room.
	- A trading agent only observes current prices but it might not know the trends and where this prices are coming from.
	- A poker playing agent only observes public cards and not know the hidden cards in players hands.
- Now agent state != environment state
- Formally this is a partially observable MDP ( POMDP )
- Agent must constructs its own state representation Sa(t) eg: 
	- Naive approach is to remember the complete history St(a) = Ht.
	- Beliefs of the environment state Sa(t) , in this approach based on probation, where we determine the agent state based on probability that environment  is  in state 1 or s2 or s3  P[Se(t) = s(1)] , P[Se(t) = s(2)], .....P[Se(t) =s(i)]. 
	- Recurrent Neural Network: Sa(t) = ∂(Sa(t-1)\*Ws + Ot\*Wo ) )

## RL Agent 
#reinforcement_learning-policy 
#reinforcement_learning_value_function 
#reinforcement_learning_model

- An RL agent may include one or more of these components 
	- Policy : agents behaviour function , this is how agent picks its actions.
	- Value function : how good is to be in a particular state and/or how good is to take a particular action , how much reward to expect if we take that  action in this particular state.
	- Model : agents representation of the environment. how agent thinks the environment works.

### Policy 

- A policy is the agents behaviour
- it is a map from state to action , eg 
- Deterministic policy: a = π(s).
action = policy(State)
- Stochastic policy : 
          π(a|s) = P[A = a| S = s]
![[Screenshot 2023-04-20 at 5.20.07 PM.png]]


### Value Function

- Value function is a prediction of future reward.
- Used to evaluate the goodness / badness of states.
- And therefore to select between actions e.g : 
Vπ(S) = Eπ( R(t)  + x*R(t+1) + x^2*R(t+2) ... | S(t) = s)

value function for a policy  = Expectation of  future reward of an action/policy over the time t , t+1 , t+2 .. given a particular state.

i.e how much total reward we can get from some state onwards if we follow this particular behaviour.  

![[Screenshot 2023-04-20 at 5.20.47 PM.png]]

### Model

- A model predicts what the environment will do next to try to learn the behaviour of the environment and use that model of the environment to help figure out what to do next.

	- **Transitions** : T predicts the next state (i.e. dynamics)
	- Rewards : R predicts the next (immediate) reward. eg:
![[Screenshot 2023-04-20 at 5.21.28 PM.png]]

### Categorizing RL agent

1. Value Based
   - *No policy (Implicit)*
   - Value function 
2. Policy Based
   - Policy
   - *No value function*
3. Actor Critic
   - Policy
   - Value Function

1. Model Free
    - Policy and value function 
    - No model
2. Model Based 
    - Policy and value function
    - Model

## Problems within Reinforcement Learning

Two fundamental problems in sequential decision making 
- Reinforcement Learning:
	  - The environment is initially unknown
	  - The agent interacts with the environment
	  - The agent improves its policy
	(Exploration - finds more information about the environment)

![[Screenshot 2023-04-20 at 5.22.21 PM.png]]
- Planning:
	  - A model of the environment is known
	  - the agent performs computation with its model(without any external interaction)
	  - The agent improves its policy
	(Exploitation  - exploits the known information to maximize reward)

![[Screenshot 2023-04-20 at 5.22.33 PM.png]]

It is usually important to both explore and exploit , balance between both is necessary.
![[Screenshot 2023-04-20 at 5.19.13 PM.png]]