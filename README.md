# Playing Atari Games with Deep Reinforcement Learning

This repository contains an implementation of a Double Deep Q-Network (DDQN) for playing the Atari game Space Invaders. The project draws inspiration from the original work by Mnih et al. (2013), "Playing Atari with Deep Reinforcement Learning". The model is a convolutional neural network that learns control policies directly from high-dimensional sensory input using reinforcement learning.

## Technical Overview

The core of this project is the application of the DDQN algorithm, an extension of the standard DQN, which helps to mitigate the overestimation of Q-values. The network architecture is based on the convolutional layers that process raw pixel data from the game frames.

### Model Architecture

The DDQN model consists of the following layers:

- Input layer that takes in the preprocessed stack of frames representing the current state.
- Convolutional layers for automatic feature extraction from the input frames.
- Fully connected layers that interpret the features from the convolutional layers and output the Q-values for each action.

### Training Process

- **Preprocessing**: The Atari frames are preprocessed to 84x84x4 grayscale images to reduce computational requirements.
- **Exploration-Exploitation Strategy**: Epsilon-greedy strategy to balance exploration of the game environment and exploitation of the learned policies.
- **Experience Replay**: Implemented to randomly sample from past experiences, improving data efficiency and breaking correlation between consecutive learning updates.
- **Fixed Q-Targets**: A separate target network, with its weights frozen and updated periodically, is used to generate the Q-value targets used in the loss function.
