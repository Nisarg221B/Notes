
for AWS deep racer
  
In order to calculate an appropriate reward you need information about the state of the agent and perhaps even the environment. These are provided to you by the AWS DeepRacer system in the form of input parameters - in other words, they are parameters for input into your reward function.

The reward function is written in Python as a standard function, but it must be called _reward_function_ with a single parameter - which is a Python dictionary containing all the input parameters provided by the AWS DeepRacer system.

There are over 20 parameters available for use, and the reward function is simply a piece of code which uses the input parameters to do some calculations and then output a number, which is the reward.

refer AWS deep racer developer pdf for details on parameters and other things.