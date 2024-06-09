# DQN
Implementation of a Deep Q Network to solve Open AI's GYM Environment 

Deep Q Learning - Lab
Introduction:
This notebook is a continuation of Andrew's Ng's Reinforcement Lab in the Coursera Machine Learning Specialty covering an implementation of a Deep Q Network model(Mnih, 2015) to solve Open AI's Lunar Landar environment.
In addition to the implementation of the lab - the following ideas are explored:

1. The effect of modifying the epsilon decay function on training stability
2. The effect of incorporating batch normalization on training stability and task completion time - (Iofee & Szegedy, 2015)

Deep Q Networks (DQN) (Mnih, 2015)
Mnih and team developed the Deep Q Network (DQN) as a general solution for reinforcement learning agents in continuous environments with high dimensional sensory inputs and actions. Previous reinforcement learning agents have shown success in limited domains with handcrafted features and domains with low-dimensional state spaces, but have yet to show promise in the high dimensional space. The intent of the DQN is to pair the abilities of Deep Neural Networks to learn abstract representations of the data with 2 optimization techniques to hurdle over the instability obstacles that come with non-linear solvers in continuous reinforcement learning problems. Experience Replay and Fixed Q Targets are the techniques proposed by Mnih and team that provides stability of the learning process (details explained below).

##### Experience Replay
Experience Replay works to stabalize the reinforcement learning model by storing experiences in a data structure and by using mini-batching techinques to sample the training data. Mnih notes that the inclusion of the experience replay mechanism is biologically inspired by observing the hipoocampus in mammals. Specifically this technique is attempting to mimic how neural patterns are reactivated "offline" or during sleep to further reinforce and refine neural connections based on past experiences.

Within the memory buffer, where experiences are stored, a random mini-batch of experiences are sampled. Not only does this help reduce the variance of updates (doesn't help getting training experiences from the same episode) but it also breaks the correlation between consecutive experiences (which would lead to the model getting trapped by a certain policy).


##### Fixed Q Target
The Fixed Q Target technique is another technique employed to stabilize the reinforcement algorithm by creating 2 Neural Networks: 
- Target Q_Network: This NN will have weights fixed for every N steps (until update) - $Q'(s,a; \theta^-)$
- Q_Network: This NN is the network that is being trained -  $Q(s,a; \theta)$

By keeping the Target_Q_Network fixed for a certain period, the target values are more stable - reducing the risk of divergence and oscillation.
