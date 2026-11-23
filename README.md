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

## Deep Q-Learning (DQN)

Deep Q-Learning (DQN) is a reinforcement learning method that combines Q-Learning with a deep neural network. Instead of storing Q-values in a lookup table, DQN uses a neural network to estimate the value of each available action based on the current traffic state.

At each decision point, the agent observes the traffic conditions, selects an action (for example, extending the current green phase or switching to another phase), and receives a reward based on traffic conditions. Through repeated interactions with the simulation, the neural network learns which actions tend to produce better outcomes.

### 1. DQN Target Value

The DQN algorithm calculates the target Q-value using the following equation:

$$
y = r + \gamma \max_{a'} Q_{\text{target}}(s',a')
$$

### 2. DQN Loss Function

The neural network is trained by minimizing the squared difference between the target Q-value and the Q-value predicted by the online network.

$$
\text{Loss} = \left[y-Q_{\text{online}}(s,a)\right]^2
$$

### 3. Parameters

* **Q_online(s, a):** Q-value predicted by the online neural network currently being trained.
* **Q_target(s', a'):** Q-value predicted by the target network for the next state.
* **r:** Immediate reward received after taking the action.
* **γ (Gamma):** Discount factor; determines the importance of future rewards.
* **s':** Next state observed after taking the action.
* **a':** Possible action in the next state.
* **y:** Target Q-value calculated using the immediate reward and estimated future reward.
* **Loss:** Measures the difference between the predicted Q-value and the target Q-value.

### 4. Explanation

Unlike traditional Q-Learning, which stores Q-values in a table, DQN uses a neural network to estimate Q-values for different traffic signal control actions.

The network takes traffic conditions, such as queue lengths, vehicle counts, waiting times, and the current signal phase, as inputs and predicts Q-values for available actions.

Through repeated interactions with the traffic simulation, the agent gradually learns which signal control actions maximize cumulative rewards and improve traffic conditions.

DQN also uses **Experience Replay** and a **Target Network** to improve training stability.



Cumulative Reward and Queue Length Comparison of Fixed-Time, Q-Learning, and Deep Q-Learning:

### Fixed-Time Signal Control
![Fixed-Time Signal Control](./Fixed%20Signal.PNG)

### Q-Learning
![Q-Learning](./Q-Learning.PNG)

### Deep Q-Learning (DQN)
![Deep Q-Learning](./Deep%20Q-Learning.PNG)
