Download link :https://programming.engineering/product/cs540-hw10-reinforcement-learning-with-q-learning/

# CS540-HW10-Reinforcement-Learning-with-Q-Learning
CS540 HW10 Reinforcement Learning with Q-Learning
1 Getting started

Download the starter code from canvas. It consists of two files: Q-Learning.py and tests.py.

You can create and activate your virtual environment with the following commands:

python3 -m venv /path/to/new/virtual/environment

source /path/to/new/virtual/environment/bin/activate

Once you have sourced your environment, you can run the following commands to install the necessary dependencies:

pip install –upgrade pip

pip install torch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0

pip install gym==0.23.1 pygame==2.1.2

You should now have a virtual environment which is fully compatible with the skeleton code.

You should set up this virtual environment on an instructional machine to do your final testing.

2 Q-Learning

We will be using the environment FrozenLake-v1 from OpenAI gym. This is a discrete environment where the agent can move in the cardinal directions, but is not guaranteed to move in the direction it chooses. The agent gets a reward of 1 when it reaches the tile marked G, and a reward of 0 in all other settings. You can read more about FrozenLake (it is the same as FrozenLake v0) here: https://gymnasium.farama.org/environments/toy_text/frozen_lake/. You will not need to change any code outside of the area marked TODO, but you are free to

change the hyper-parameters if you want to. For each sampled tuple (s, a, r, s0, done), the


update rule for Q-learning is

The agent should act according to an epsilon-greedy policy as defined in the Reinforcement Learning slides. In this equation, alpha is the learning rate hyper-parameter, and gamma is the discount factor.

HINT: tests.py is worth looking at to gain an understanding of how to use the OpenAI


gym env.

Files to Submit: For this section, you should submit the files Q_learning.py and Q_TABLE.pkl.

3 OpenAI gym Environment

You will need to use several OpenAI gym functions in order to operate your gym environment for reinforcement learning. As stated in a previous hint, tests.py has a lot of the function calls you need. Several important functions are as follows:

env.step(action)

Given that the environment is in state s, step takes an integer specifying the chosen action, and returns a tuple of the form (s, r, done, info). ’done’ specifies whether or not s0is the final state for that particular episode, and ’info’ is unused in this assignment. env.reset()

Resets the environment to its initial state, and returns that state.

env.action space.sample()

Samples an integer corresponding to a random choice of action in the environment’s action space.

env.action space.n

In the setting of the environments we will be working with for these assignments, this is an integer corresponding to the number of possible actions in the environment’s action space.

You can read more about OpenAI gym here: https://gymnasium.farama.org.

4 Testing

There are two ways to test for this assignment.

For local testing: First call python3 Q_learning.py, which will generate a file called

Q_TABLE.pkl Next, call python3 ./tests.py in the released folder and it will give you a score. This test.py file is the same file we will be using to test on our machines so the score you get will very likely be the same as your final score.

For canvas testing: Same as previous assignments, submit to canvas as specified below and you will get a score.

4 Submission

Once again, you can test your learned policies, by calling python3 ./tests.py. Make sure to test your saved Q-tables using tests.py on the instructional machines with a virtual environment set up as specified above. This is the same program, which we will be using to test your Q-tables and Q-network, so you will have a good idea about how many points you will receive for the automated tests portion of the grade. Your submission should contain the following files:


Required: Q learning.py, Q TABLE.pkl

Please submit these files in a zipped folder title <yournetid>.zip , where ’yournetid’ is your net ID. Please make sure that there is not a folder inside the zipped folder, and that the submitted files are at the top level of the zipped folder.

The assignment is due May 4th at 9:30AM central time. We are not accepting late submissions for this assignment. Regrades will only be accepted if they are due to an error in tests.py.
