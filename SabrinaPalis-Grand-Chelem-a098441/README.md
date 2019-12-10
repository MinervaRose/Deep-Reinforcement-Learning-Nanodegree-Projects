# Grand-Chelem
![robot_tennis_header-01](https://user-images.githubusercontent.com/39020690/64225876-48f11780-ceab-11e9-8e36-f4e2ed5f3084.png)

DRLND Collaboration and Competition

This repository contains my submission to the third project of the [Udacity's Deep Reinforcement Learning Nanodegree program](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893).
All of the code is in PyTorch (v0.4) and Python 3. 

*Only interested in the implementation? [Read the report now](https://github.com/SabrinaPalis/Grand-Chelem/blob/master/report.pdf).*

The present README file:

:small_blue_diamond: describes the project environment details (i.e., the state and action spaces, and when the environment is considered solved).

:small_blue_diamond: has instructions for installing dependencies or downloading needed files.

:small_blue_diamond: describes how to run the code in the repository to train the agent.


# Objective


![tennis](https://user-images.githubusercontent.com/39020690/64225910-6b833080-ceab-11e9-940e-be2597bf6b21.gif)

For this project, you will work with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

* After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.

* This yields a single score for each episode.

### Solving the Environment

The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

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

Download the Grand-Chelem repository.


### Step 3: Download the Unity Environment  

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux_NoVis.zip) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)


2. Place the file in the DRLND GitHub repository, in the `p3_continuous-control/` folder, and unzip (or decompress) the file. 

### Instructions

You can see how I trained the agent in the Jupyter notebook [Tennis.ipynb](https://github.com/SabrinaPalis/Grand-Chelem/blob/master/Tennis.ipynb) along with the trained model weights  

agent1_checkpoint_actor.pth 

agent1_checkpoint_critic.pth 

agent2_checkpoint_actor.pth 

agent2_checkpoint_critic.pth

**Please note that the code of the Jupyter notebook `Tennis.ipynb` is my submission to the DRLND Navigation project. It was run in the Udacity workspace. In order to train your own agent, please use the [Tennis-Try-it-Yourself.ipynb file](https://github.com/SabrinaPalis/Grand-Chelem/blob/master/Tennis-Try-it-Yourself.ipynb) that includes the proper indications for someone not using the Udacity workspace for training.** 

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

you may wish to have a look at [the report](https://github.com/SabrinaPalis/Grand-Chelem/blob/master/report.pdf) that I submitted as part of this project.


