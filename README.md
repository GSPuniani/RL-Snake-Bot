# RL Snake Bot

<i>This project was adapted from Vedant Goswami's [tutorial](https://www.geeksforgeeks.org/ai-driven-snake-game-using-deep-q-learning/) and [code](https://github.com/vedantgoswami/SnakeGameAI).</i>

This project showcases the power of reinforcement learning as an AI tool. Here, we use reinforcement learning to train a bot in a game of "Snake". In this arcade game, a player controls the direction of a blocky snake that doesn't stop moving. It grows in length as it eats food, which appears at a random spot on the screen. The object of the game is to keep the snake alive as along as possible by not letting it collide with a wall or intersect with itself. 

## Setup

Clone this repo onto your local machine. Create and activate a virtual environment, and then install the necessary packages (`pygame`, `torch`, etc.):
 - `python3 -m venv venv`
 - `source venv/bin/activate`
 - `pip install pygame`
 - `pip install torch`
 - `pip install` etc., as needed

Take some time to read through the code. Check your understanding by answering the `TODO` prompts. When you're ready to start training the model, run the `agent.py` module. It will open up a GUI window that automatically runs the game over and over. After around 60-70 games, you should start to see some improvement in the performance of the model. Feel free to run the model as long as you want. When you're ready to stop, you will need to manually terminate the program by entering Ctrl-C in the Terminal. 

There should be a `matplotlib` chart that displays the score over time, but it is currently prevented from showing up. As a bonus objective, try to figure out how to display the chart (created in `helper.py`) such that it does not crash the program.


## Reinforcement Learning
In Reinforcement Learning, there are three main components: the <b>environment</b> (our game), the <b>model</b> (implemented with simple Q-learning or a neural network), and the <b>agent</b> (the snake). Every time the agent performs an action, the environment gives a reward to the agent, which can be positive or negative depending on how good the action was from that specific state.
<p align="center">
<img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/structure.svg" height="380px" width="480px">
  </p>
Deep Reinforcement Learning (DRL) combines the above ideas of RL with deep neural networks. The neural network learns the “Q function”, which takes in as input the current environment state and outputs a vector containing expected rewards for each possible action. The agent can then pick the action that maximizes the Q function. Based on this action, the game then updates the environment to a new state and assigns a reward (e.g. +10 for eating an apple, -10 for hitting a wall). At the beginning of training, the Q function is just approximated by a randomly initialized neural network. 

### Algorithm
The snake and food on the board randomly placed.
* Calculate the state of the snake using the 11 values 
  <img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/State.svg">
* Now this current state is passed to the RL Model for the next state.
  <img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/Model.svg">
* After executing the next state, calculate the reward. Rewards are defined as below:
  1. Eat food  :  +10
  2. Game Over :  -10
  3. Else      :    0
* Update the Q value and Train the Model.


The algorithm is divided into three Modules: <b>Agent</b> (`agent.py`), <b>Game</b> (`snake_gameai.py`), and <b>Model</b> (`model.py`).
  <p align='center'>
    <img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/agentstate.PNG" width=400px height=290px>
  </p>
  <p>
    <img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/game.png" width=390px height=250px align='left'>
    <img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/model.png" width=390px height=250px align='right'>
  </p>

<br><br><br><br><br><br><br><br><br><br><br><br>
<hr />
<p>
  <h2>Result</h2>
<img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/new.gif" width=380px height=250px align='left'>
<img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/Animation.gif" width=380px height=250px align='right'>
<br><br><br><br><br><br><br><br><br><br><br>
<p style="font-size:25px">
<pre>              <b> Initial Epochs</b>                                           <b>After 100+ Epochs</b></pre>
</p>
