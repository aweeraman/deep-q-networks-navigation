# Project: Navigation

This is a project that uses Deep Q-Networks to train an agent to capture yellow bananas and avoid
blue bananas through deep reinforcement learning in a Unity ML-Agents environment.

## Learning algorithm

Q-Learning is an approach which generates a Q-table that is used by an agent to determine best action
for a given state. This technique becomes difficult and inefficient in environments that have a large
state space. Deep Q-Networks on the other hand makes use of a neural network to approximate Q-values
for each action based on the input state.

However, there are drawbacks in Deep Q-Learning. A common issue is that the reinforcement learning tends
to be unstable or divergent when a non-linear function approximator such as neural networks are used to
represent Q. This instability comes from the correlations present in the sequence of observations, the fact
that small updates to Q may significantly change the policy and the data distribution, and the correlations
between Q and the target values. [1]

To overcome this, experience replay is a technique that was used in this solution that uses the biologically
inspired approach of replaying a random sample of prior actions to remove correlations in the observation
sequence and smooth changes in the data distribution.

## Model architecture and hyperparameters

* Fully connected layer 1: Input 37 (state space), Output 32, RELU
* Fully connected layer 2: Input 32, Output 32, RELU
* Fully connected layer 3: Input 32, Output 4 (action space)

The hyperparameters for tweaking and optimizing the learning algorithm were:

* max_t (750): maximum number of timesteps per episode
* eps_start (1.0): starting value of epsilon, for epsilon-greedy action selection
* eps_end (0.01): minimum value of epsilon
* eps_decay (0.9): multiplacative factor (per episode) for decreasing epsilon

## Plot of rewards

Below is a training run of the above model architecture and hyperparameters:

```
Number of agents: 1
Number of actions: 4
Episode 100	Average Score: 3.97
Episode 200	Average Score: 9.51
Episode 287	Average Score: 13.12
Environment solved in 187 episodes!	Average Score: 13.12
```

The plot of rewards for this run is as follows:

![Plot of rewards](https://raw.githubusercontent.com/aweeraman/deep-q-networks-navigation/master/graph.png)

## Ideas for future work

Further optimization of this architecture can be performed by training with different hyperparameters to
get faster and better learning outcomes. A couple of further approaches to try out are:

* Double Q-Learning
* Delayed Q-Learning

## Reference

1 - https://en.wikipedia.org/wiki/Q-learning#Deep_Q-learning
