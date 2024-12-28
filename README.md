# DQN
Implementation of a Deep Q Network to solve Open AI's GYM Environment 

Deep Q Learning - Lab
Introduction:
This notebook is a continuation of Andrew's Ng's Reinforcement Learning Lab in the Coursera Machine Learning Specialty covering an implementation of a Deep Q Network model(Mnih, 2015) to solve Open AI's Lunar Landar environment.
In addition to the implementation of the lab - the following ideas are explored:

1. The effect of modifying the epsilon decay function on training stability
2. The effect of incorporating batch normalization on training stability and task completion time - (Iofee & Szegedy, 2015)


<video controls>
    <source src="videos/rl-video-episode-2.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>


Deep Q Networks (DQN) (Mnih, 2015)
Mnih and team developed the Deep Q Network (DQN) as a general solution for reinforcement learning agents in continuous environments with high dimensional sensory inputs and actions. Previous reinforcement learning agents have shown success in limited domains with handcrafted features and domains with low-dimensional state spaces, but have yet to show promise in the high dimensional space. The intent of the DQN is to pair the abilities of Deep Neural Networks to learn abstract representations of the data with 2 optimization techniques to hurdle over the instability obstacles that come with non-linear solvers in continuous reinforcement learning problems. Experience Replay and Fixed Q Targets are the techniques proposed by Mnih and team that provides stability of the learning process.

Repo Summary: 
- Deep_Q_Learning_Moon.ipynb: notebook file containing training loop
- Test_Env.ipynb: notebook file containing recording environment of trained lunar lander
