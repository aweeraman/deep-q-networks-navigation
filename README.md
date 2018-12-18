# Udacity Deep Reinforcement Learning Nanodegree Project 1: Navigation

This is a project that uses Deep Q-Networks to train an agent to capture yellow bananas and avoid
blue bananas through deep reinforcement learning in a Unity ML-Agents environment.

The steps below will describe how to get this running on MacOS:

## 1. Clone the repo

```
$ git clone https://github.com/aweeraman/deep-q-networks-navigation.git
```

## 2. Install Python & dependencies

Using the Anaconda distribution, create a new python runtime and install the required dependencies:

```
$ conda create -n dqn python=3.6
$ source activate dqn
$ pip install -r requirements.txt
```

## 3. Install the Unity Environment

Download a pre-built environment to run the agent. You will not need to install Unity for this. The
environment is OS specific, so the correct version for the operating system must be downloaded.

For MacOS, [use this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)

After uncompressing, there should be a directory called "Banana.app" in the root directory of the repository.

## 4. Run the agent

To run the pre-trained agent, execute the following:

```
$ python bananas.py --run
Mono path[0] = '/Users/anuradha/ninsei/udacity/bananas/Banana.app/Contents/Resources/Data/Managed'
Mono config path = '/Users/anuradha/ninsei/udacity/bananas/Banana.app/Contents/MonoBleedingEdge/etc'
INFO:unityagents:
'Academy' started successfully!
Unity Academy name: Academy
        Number of Brains: 1
        Number of External Brains : 1
        Lesson number : 0
        Reset Parameters :

Unity brain name: BananaBrain
        Number of Visual Observations (per agent): 0
        Vector Observation space type: continuous
        Vector Observation space size (per agent): 37
        Number of stacked Vector Observation: 1
        Vector Action space type: discrete
        Vector Action space size (per agent): 4
        Vector Action descriptions: , , ,
Number of agents: 1
Number of actions: 4
States look like: [1.         0.         0.         0.         0.84408134 0.
 0.         1.         0.         0.0748472  0.         1.
 0.         0.         0.25755    1.         0.         0.
 0.         0.74177343 0.         1.         0.         0.
 0.25854847 0.         0.         1.         0.         0.09355672
 0.         1.         0.         0.         0.31969345 0.
 0.        ]
States have length: 37
Score: 15.0
```

To customize hyperparameters and train the agent, execute the following:

```
$ python bananas.py --train
(drl) sendai:bananas anuradha$ python bananas.py --train
Mono path[0] = '/Users/anuradha/ninsei/udacity/bananas/Banana.app/Contents/Resources/Data/Managed'
Mono config path = '/Users/anuradha/ninsei/udacity/bananas/Banana.app/Contents/MonoBleedingEdge/etc'
INFO:unityagents:
'Academy' started successfully!
Unity Academy name: Academy
        Number of Brains: 1
        Number of External Brains : 1
        Lesson number : 0
        Reset Parameters :

Unity brain name: BananaBrain
        Number of Visual Observations (per agent): 0
        Vector Observation space type: continuous
        Vector Observation space size (per agent): 37
        Number of stacked Vector Observation: 1
        Vector Action space type: discrete
        Vector Action space size (per agent): 4
        Vector Action descriptions: , , ,
Number of agents: 1
Number of actions: 4
Episode 100	Average Score: 0.785
Episode 200	Average Score: 4.03
Episode 300	Average Score: 7.21
Episode 400	Average Score: 9.00
Episode 500	Average Score: 11.44
Episode 600	Average Score: 13.50
Episode 700	Average Score: 15.07
Episode 800	Average Score: 15.16
Episode 900	Average Score: 15.90
Episode 1000	Average Score: 16.83
```

# Troubleshooting

If you run into an error such as the following when training the agent:

```
ImportError: Python is not installed as a framework. The Mac OS X backend will not be able to function correctly if Python is not installed as a framework. See the Python documentation for more information on installing Python as a framework on Mac OS X. Please either reinstall Python as a framework, or try one of the other backends. If you are using (Ana)Conda please install python.app and replace the use of 'python' with 'pythonw'. See 'Working with Matplotlib on OSX' in the Matplotlib FAQ for more information.
```

Modify ~/.matplotlib/matplotlibrc and add the following line:

```
backend: TkAgg
```
