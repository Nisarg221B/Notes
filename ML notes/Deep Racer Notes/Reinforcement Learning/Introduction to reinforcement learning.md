
previous section - [[Introduction to machine learning]]
next - 

#deep_racer
#deep_racer_Section_2

#reinforcement_learning 

Reinforcement learning consists of several key concepts:

-   **Agent** is the entity being trained. In our example, this is a dog.
-   **Environment** is the “world” in which the agent interacts, such as a park.
-   **Actions** are performed by the agent in the environment, such as running around, sitting, or playing ball.
-   **Rewards** are issued to the agent for performing good actions.

With AWS deep racer 


-   The **agent** is the AWS DeepRacer car (or, more specifically, the software running on the car);
-   The agent wants to achieve the goal of finishing laps around the track as fast as possible, so the track is the **environment**.
-   The agent knows about the environment through the **state** which is the portion of the environment known to the agent. In the case of AWS DeepRacer, it is the images being captured by the camera.
-   Once the agent knows its state in the environment, it can perform **actions** in the environment to help it achieve its goal. In the case of DeepRacer, this might be accelerating, braking, turning left, turning right, or going straight.
-   The agent then receives feedback in the form of a **reward** about how well that action contributed towards achieving its goal.
-   And all this happens within an **episode**. This can be thought of as a cycle of the agent performing an action in the environment (based upon the state it has observed) and then receiving feedback in the form of a reward which informs future actions it might take.

AWS DeepRacer offers two training algorithms:

-   Proximal Policy Optimisation (PPO)
-   Soft Actor Critic (SAC)

## Policy 
#reinforcement_learning-policy 
A policy defines the action that the agent should take for a given state.

- **Deterministic policy**
Its a policy where there is a direct relationship between state and action. This is often used when the agent has a full understanding of the environment and, given a state, always performs the same action.

- **Stochastic policy** (AWS deep-racer)
In a stochastic policy you have a range of possible actions for a state, each with a probability of being selected. When the policy is queried to return an action for a state it selects one of these actions based on the probability distribution.

With a stochastic policy how do you determine the value of being in a particular state and update the probability for the action which got us into this state? This question can also be applied to a deterministic policy; how do we pick the action to be taken for a given state?  
  
Well, we somehow need to determine how much benefit we have derived from that choice of action. We can then update our stochastic policy and either increase or decrease the probability of that chosen action being selected again in the future, or select the specific action with the highest likelihood of future benefit as in our deterministic policy.  
  
If you said that this is based on the reward, you are correct. However, the reward only gives us feedback on the value of the single action we just chose. To truly determine the value of that action (and resulting state) we should not only look at the current reward, but future rewards we could possibly get from being in this state this is done through #reinforcement_learning_value_function

## Value function 

**value function**. Think of this as looking ahead into the future and figuring out how much reward you expect to get given your current policy.

Say the DeepRacer car (agent) is approaching a corner. The algorithm queries the policy about what to do, and it says to accelerate hard. The algorithm then asks the value function how good it thinks that decision was - but unfortunately the results are not too good, as it’s likely the agent will go off-track in the future due to his hard acceleration into a corner. As a result, the value is low and the probabilities of that action can be adjusted to discourage selection of the action and getting into this state.

**value function is used to critique the policy, encouraging desirable actions while discouraging others.

![[Screenshot 2023-03-26 at 7.13.18 PM.png|600]]

We call this adjustment a **policy update**, and this regularly happens during training. In fact, you can even define the number of episodes that should occur before a policy update is triggered.

![[Screenshot 2023-03-26 at 7.12.31 PM.png]]

The reinforcement learning algorithm will estimate the value function from past data and experience.

