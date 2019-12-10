<img src="https://user-images.githubusercontent.com/39020690/63669691-b5339300-c7a8-11e9-876b-d492f1781bc9.png">

# Going-bananas 

This repository contains my submission to the first project of the [Udacity's Deep Reinforcement Learning Nanodegree program](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893).
All of the code is in PyTorch (v0.4) and Python 3. 

*Only interested in the implementation? [Read the report now](https://github.com/SabrinaPalis/Going-bananas/blob/master/Report.pdf).*

The present README file:

:small_blue_diamond: describes the project describes the the project environment details (i.e., the state and action spaces, and when the environment is considered solved).

:small_blue_diamond: has instructions for installing dependencies or downloading needed files.

:small_blue_diamond: describes how to run the code in the repository to train the agent.


# Objective

<img src="https://user-images.githubusercontent.com/39020690/63669633-861d2180-c7a8-11e9-8973-458d65eb995f.gif">


For this project, you will train an agent to navigate (and collect bananas!) in a large, square world. 

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

* :zero: - move forward.
* :one: - move backward.
* :two: - turn left.
* :three: - turn right.

The task is episodic, and **in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.**

### Note

*The project environment is similar to, but not identical to the Banana Collector environment on the [Unity ML-Agents GitHub page](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#banana-collector).
The Udacity project submission used the environment that was provided as part of the project and not the one on the ML-Agents GitHub page.*

# The Environment 

Follow the instructions below to explore the environment on your own machine.

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

## Step 3: Download the Unity Environment 

Download the environment from one of the links below. You need only select the environment that matches your operating system:

:small_blue_diamond: Linux: click [here](
https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)

:small_blue_diamond: Mac OSX: click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)

:small_blue_diamond: Windows (32-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)

:small_blue_diamond: Windows (64-bit): click [here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)


Then, place the file in the at the root of the Going-bananas GitHub repository, and unzip (or decompress) the file.

(For Windows users) Check out this [link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(For AWS) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use this [link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the Linux operating system above.)

# Training the agent

:banana: **Please note that the code of the Jupyter notebook Navigation.ipynb is my submission to the DRLND Navigation project. It was run in the Udacity workspace. In order to train your own agent, please use the [Navigation-Try-it-Yourself.ipynb file](https://github.com/SabrinaPalis/Going-bananas/blob/master/Navigation-Try-it-Yourself.ipynb) that includes the proper indications for you to change the file_name parameter to match the location of the Unity environment that you downloaded.** :banana:

You can see how I trained the agent in the Jupyter notebook [Navigation.ipynb](https://github.com/SabrinaPalis/Going-bananas/blob/master/Navigation.ipynb) along with the trained model weights [project1_dqn_agent.pth](https://github.com/SabrinaPalis/Going-bananas/blob/master/project1_dqn_agent.pth). 

In order to train your own agent, please use the [Navigation-Try-it-Yourself.ipynb file](https://github.com/SabrinaPalis/Going-bananas/blob/master/Navigation-Try-it-Yourself.ipynb) that includes the proper indications for you to change the file_name parameter to match the location of the Unity environment that you downloaded.

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

you may wish to have a look at [the report](https://github.com/SabrinaPalis/Going-bananas/blob/master/Report.pdf) that I submitted as part of this project.







