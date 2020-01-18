
![robot_reacher_header](https://user-images.githubusercontent.com/39020690/64061198-2c03ce00-cba5-11e9-9a0d-79d3c4e32a54.png)


# Gotta-get-it

This repository contains my submission to the first project of the [Udacity's Deep Reinforcement Learning Nanodegree program](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893).
All of the code is in PyTorch (v0.4) and Python 3. 

*Only interested in the implementation? [Read the report now](https://github.com/SabrinaPalis/Deep-Reinforcement-Learning-Nanodegree-Projects/blob/master/SabrinaPalis-Gotta-get-it-bd72ba5/report.pdf).*

The present README file:

:small_blue_diamond: describes the project environment details (i.e., the state and action spaces, and when the environment is considered solved).

:small_blue_diamond: has instructions for installing dependencies or downloading needed files.

:small_blue_diamond: describes how to run the code in the repository to train the agent.



# Objective


![20_arms](https://user-images.githubusercontent.com/39020690/64061215-6bcab580-cba5-11e9-92ce-055a681ee005.gif)          

For this project, you will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### Distributed Training

For this project, we will provide you with two separate versions of the Unity environment:
- The first version contains a single agent.
- The second version contains 20 identical agents, each with its own copy of the environment.  

The second version is useful for algorithms like [PPO](https://arxiv.org/pdf/1707.06347.pdf), [A3C](https://arxiv.org/pdf/1602.01783.pdf), and [D4PG](https://openreview.net/pdf?id=SyZipzbCb) that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience.  

### Solving the Environment

Note that your project submission need only solve one of the two versions of the environment. 

#### Option 1: Solve the First Version

The task is episodic, and in order to solve the environment,  your agent must get an average score of +30 over 100 consecutive episodes.

#### Option 2: Solve the Second Version

The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents.  In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents).  Specifically,
- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent.  This yields 20 (potentially different) scores.  We then take the average of these 20 scores. 
- This yields an **average score** for each episode (where the average is over all 20 agents).

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30. 


**Follow the instructions below to explore the environment on your own machine**

## Step 1: Dependencies

By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

(For Windows users) The ML-Agents toolkit supports Windows 10. While it might be possible to run the ML-Agents toolkit using other versions of Windows, it has not been tested on other versions. Furthermore, the ML-Agents toolkit has not been tested on a Windows VM such as Bootcamp or Parallels. 

1. Create (and activate) a new environment with Python

:small_blue_diamond: Linux or Mac:

> conda create --name drlnd python=3.6
> source activate drlnd

:small_blue_diamond: Windows:

> conda create --name drlnd python=3.6 
> activate drlnd

2. Follow the instructions in this [repository](https://github.com/openai/gym) to perform a minimal install of OpenAI gym.

:small_blue_diamond: Next, install the classic control environment group by following the instructions [here](https://github.com/openai/gym#classic-control).

:small_blue_diamond: Then, install the box2d environment group by following the instructions [here](https://github.com/openai/gym#box2d).

3. Clone the repository (if you haven't already!), and navigate to the python/ folder. Then, install several dependencies.

> git clone https://github.com/udacity/deep-reinforcement-learning.git
> cd deep-reinforcement-learning/python
> pip install .

4. Create an [IPython kernel](https://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the drlnd environment.

> python -m ipykernel install --user --name drlnd --display-name "drlnd"

5. Before running code in a notebook, change the kernel to match the drlnd environment by using the drop-down Kernel menu.

## Step 2: Download the present repository

Download the Going-bananas repository.


### Step 3: Download the Unity Environment  

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:

    - **_Version 1: One (1) Agent_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    - **_Version 2: Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the DRLND GitHub repository, in the `p2_continuous-control/` folder, and unzip (or decompress) the file. 

### Instructions

You can see how I trained the agent in the Jupyter notebook [Continuous_Control.ipynb](https://github.com/SabrinaPalis/Gotta-get-it/blob/master/Continuous_Control.ipynb) along with the trained model weights  checkpoint_actor.pth and checkpoint_critic.pth.

**Please note that the code of the Jupyter notebook `Continuous_Control.ipynb` is my submission to the DRLND Navigation project. It was run in the Udacity workspace. In order to train your own agent, please use the [Continuous_Control-Try-it-Yourself.ipynb file](https://github.com/SabrinaPalis/Gotta-get-it/blob/master/Continuous_Control-Try-it-Yourself.ipynb) that includes the proper indications for someone not using the Udacity workspace for training.** 

To run the notebook, first start up the Jupyter server with the following command.

> (base)$ conda activate drlnd
>
> (drlnd)$ jupyter notebook
>
> [I 07:12:35.811 NotebookApp] Serving notebooks from local directory: /home/handol/Code
>
> ...
>
>     Copy/paste this URL into your browser when you connect for the first time,
>
>     to login with a token:
>
>        http://localhost:8888/?token=e406adf4c029503d5eae4888ec3bc9eb8b7f9a653e9d06bd
>

It will open up the web browser. If not, open the browser manually and go to the URL as noted in the output.

Then you need to run each cell and you can see the ouput as you go.

# The algorithm

To know more about the 

:small_blue_diamond: algorithm 

:small_blue_diamond: hyperparameters

:small_blue_diamond: model architecture

you may wish to have a look at [the report](https://github.com/SabrinaPalis/Deep-Reinforcement-Learning-Nanodegree-Projects/blob/master/SabrinaPalis-Gotta-get-it-bd72ba5/report.pdf) that I submitted as part of this project.



