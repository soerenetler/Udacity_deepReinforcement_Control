# Report
## The learning approach

To solve the descriped environment a deep deterministic policy gradient (DDPG) algorithm is deployed. This approach is very similar to DQNs and can be used in contious action spaces like the four continous action variables we have in this environment. The actor of the DDPG learns a (deterministic) policy directly predicting the best possible action at state s. The cretic is trained to approximate the optimal action value function and evaluate it for the best action chosen by the actor.

Similar to the DQN the DDPG also uses a replay buffer and a target network for a more stable trainig process.

The DDPG algorithm learns a deterministic policy to Gaussian noise is added to also allow exploratory characteristics. This noise is decreased over the training episodes.

## Implementation
The implementation is very similar to the one in the privious project (https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-bipedal). The code is addapted to the unity environment and changed for multiple agents. Additional mechanisms like batch normalisation, gradient clipping and updating the network only 10 times every 20 steps are implemented

The hyperparameters are tuned to evaluate their impact on training performance.

## Hyperparameter
The model contains the following hyperparamter. the parameter value are based on the previous project in the nanodegree and yield good results.

### Layers of the DNN
The actor and the critic use a three layer architecture. The actor has 256 units in each of the layers and uses batch normalisation after the first layer. Relu functions are used for activation in the first and second layer and the output neuron uses tanh function.

The critic also has three layers with the chosen action concatenated with the output of the first layer. Again all layers consist out of 256 units.

### Other Parameters
 - BUFFER_SIZE = int(1e6)  # 1e5 replay buffer size
 - BATCH_SIZE = 128        # minibatch size
 - GAMMA = 0.99            # discount factor
 - TAU = 1e-3              # for soft update of target parameters
 - LR_ACTOR = 1e-4         # learning rate of the actor # ADDED
 - LR_CRITIC = 1e-4        # learning rate of the critic # ADDED
 - WEIGHT_DECAY = 0        # L2 weight decay
 - LEARN_EVERY = 20        # Update the networks 10 times after every 20 timesteps
 - LEARN_NUMBER = 10       # Update the networks 10 times after every 20 timesteps
 - EPSILON = 1.0           # Noise factor
 - EPSILON_DECAY = 0.999999  # Noise factor decay

## Learning Curve
![Reward curve](learning.png?raw=true)

## Further improvements
I could not get the model to also solve an environment with a single agent. The training was very slow and took several hours with only little progress (a maximum score of about 6). A next step for improvement would be to speed up the trainign process.

Another improvement could be the TD3 algorithm. It has three major improvemnts to DDPG: a twin Q-network, Gaussian noise is also added to the target action and a delayed update to the policy network (p. 408 in Deep Reinforcement Learning by Miguel Morales).