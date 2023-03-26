
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

-   Proximal Policy Optimization (PPO)
-   Soft Actor Critic (SAC)

## Policy 

A policy defines the action that the agent should take for a given state. This could conceptually be represented as a table - given a particular state, perform this action.

