# Reinforcement-learning
Developing Q-Learning and Deep Q-Learning Algorithms for Traffic Signal Control and compare results with Static Traffic Signal
# Study Area
A random intersection
# Data Collection and Analysis
Required Data: 
a. Traffic Flow parameters: Traffic Volume-Default SUMO Values and Traffic Speed-Default SUMO Values
b. Traffic Behavioral Parameters: Lane Changing Model-Default SUMO Values and Car Following Model: Default SUMO Values
c. Vehicle Types: Default SUMO Values
# Base Model Development 
Required Steps: We have to create Network and name it properly. After that, we need to add traffic cars, volume and speed. After identifying vehicle types, detectors need to add. Finally, we need to compare 3 types of traffic lights, Fixed Timing, Q-Learning and Deep Q learning

# Formula 
Q-Learning:
Q-Learning is a reinforcement-learning method that learns through interaction with the simulation. At each decision point,
the agent observes the traffic state, selects an action (for example, extend the current green or switch to another phase),and receives a reward based on traffic conditions. Over repeated experiences, it learns which actions tend to produce
better outcomes.

The Q-Learning algorithm updates the Q-value using the following equation:

<h3>Q-Learning Update Formula</h3>

<p align="center">
  <img src="https://latex.codecogs.com/svg.image?Q(s,a)%20%5Cleftarrow%20Q(s,a)%20%2B%20%5Calpha%20%5Cleft%5Br%20%2B%20%5Cgamma%20%5Cmax_%7Ba'%7D%20Q(s',a')%20-%20Q(s,a)%20%5Cright%5D" />
</p>
### Parameters

- **Q(s, a):** Current estimated value of taking action `a` in state `s`.
- **α (Alpha):** Learning rate; controls how much new experience updates the existing Q-value.
- **r:** Reward received after taking the action.
- **γ (Gamma):** Discount factor; determines the importance of future rewards.
- **s':** Next state observed after taking the action.
- **a':** Possible action in the next state.
- **max Q(s', a'):** Maximum estimated Q-value among all possible actions in the next state.

### Explanation

The Q-Learning algorithm updates its current Q-value based on the immediate reward and the maximum expected future reward. Through repeated interactions with the environment, the agent learns which actions provide the highest cumulative reward.


Cumulative Reward and Queue Length Comparison of Fixed-Time, Q-Learning, and Deep Q-Learning:

### Fixed-Time Signal Control
![Fixed-Time Signal Control](./Fixed%20Signal.PNG)

### Q-Learning
![Q-Learning](./Q-Learning.PNG)

### Deep Q-Learning (DQN)
![Deep Q-Learning](./Deep%20Q-Learning.PNG)
