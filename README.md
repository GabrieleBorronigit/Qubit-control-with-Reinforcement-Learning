# Qubit control with reinforcement learning

In this project a reinforcement learning agent learns how to drive a qubit from an initial state to a target state, using a controllable 2D external field. The qubit evolves with the Hamiltonian

H(t) = u_x(t) σ_x + u_y(t) σ_y

where u_x and u_y are the pulses chosen by the agent step by step, and the reward is based on the overlap between the final state and the target one.

The environment is written with gymnasium, and the problem is solved in two ways:

1) Discrete actions: the pulses can take only a few fixed values, and the agent is trained with a DQN written from scratch in TensorFlow.
2) Continuous actions: the pulses can take any value in [-1, 1]. Here DQN is not suitable anymore, so I implemented Soft Actor Critic (SAC) from scratch and compared it with the SAC of stable-baselines3.

The trajectories of the qubit during the episodes are plotted on the Bloch sphere.

## Files

- `RL_cubit.ipynb`: theory, environments, DQN and SAC implementations
- `RL_training.ipynb`, `RL_training2.ipynb`: training runs of the SAC agent and test on new episodes
- `RL-Qbit.pdf`: presentation of the project (also as `.pptx`)

The other deep learning exercises of the course are in [Deep-learning-laboratory-2024](https://github.com/GabrieleBorronigit/Deep-learning-laboratory-2024).
