# RL-lunar-lander
Reinforcement Learning Lunar Lander

## Task 
This task was adopted from the lecture Probabilistic Artificial Intelligence taught by Andreas Krause at ETH Zurich. In the lunar lander environment, a lander must be controlled to land between two flags on the ground. When controlling the lander, the goal is to successfully land upright on its two legs, between the flags and in a limited timeframe, whilst expending minimal fuel. Your task is to implement an algorithm that, by practicing on a simulator, learns a control policy for the lander.

## Environment and Scoring
At each discrete time step, the controller can maneuver the lander by taking one of four actions: doing nothing, firing the left engine, firing the right engine, or firing the main engine. The goal is to accumulate as much reward as possible in 300 timesteps. In this evaluation case here, after 300 timesteps the episode ends. Positive reward is obtained for landing between the flags and landing on the lander’s legs. Negative reward is obtained for firing the main engine or side engines (more negative for the main engine) or for crashing the lander. Note that the positive reward for lander is for landing on the legs: if you land so fast that the legs hit the ground followed by the main lander body, it is counted as only crashing. At each time-step, the agent gets an 8-dimensional observation (some floats, some binary), giving the lander’s motion and position relative to the flags. The score is then based upon the average performance of the learned policy after the training episodes. The final score will be the final the expected cumulative reward of the final policy over an episode.

## Model
The Model is a simple variant of a policy gradient reinforcement learning algorithm. There are two additional features to the algorithm, the first is the use of “rewards to go”. The second is the use of a generalized advantage estimate for reducing the variance of policy gradient updates. The policy and value function estimates are computed using neural networks. 
