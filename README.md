# RL Snake Bot

<i>This project was adapted from Vedant Goswami's [tutorial](https://www.geeksforgeeks.org/ai-driven-snake-game-using-deep-q-learning/) and [code](https://github.com/vedantgoswami/SnakeGameAI).</i>

This project showcases the power of reinforcement learning as an AI tool. Here, we use reinforcement learning to train a bot in a game of "Snake". In this arcade game, a player controls the direction of a blocky snake that doesn't stop moving. It grows in length as it eats food, which appears at a random spot on the screen. The object of the game is to keep the snake alive as along as possible by not letting it collide with a wall or intersect with itself. 

## Setup


## Reinforcement Learning
In Reinforcement Learning, we have two main components: the <b>environment</b> (our game) and the <b>agent</b> (our Snake.. or to be correct, the Deep Neural Network that drives our Snake’s actions). Every time the agent performs an action, the environment gives a reward to the agent, which can be positive or negative depending on <i>how good the action was from that specific state.</i>
<p align="center">
<img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/structure.svg" height="380px" width="480px">
  </p>
Deep Reinforcement Learning (DRL) combines the above ideas of RL with deep neural networks. The neural network learns the “Q function”, which takes as input the current environment state and outputs a vector containing expected rewards for each possible action. The agent can then pick the action that maximizes the Q function. Based on this action, the game then updates the environment to a new state and assigns a reward (e.g. +10 for eating an apple, -10 for hitting a wall). At the beginning of training, the Q function is just approximated by a randomly initialized neural network. 

I will explain the implementation of this SnakeAI step by step.<br>
A simple snake board game which is user controlled is designed using pygame module is here https://github.com/vedantgoswami/SnakeGameAI/blob/main/snake_game.py 

### Algorithm
We have snake and food on the board randomly placed.
* calculate the state of the snake using the 11 values 
  <img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/State.svg">
* Now this current state is passed to the RL Model for the next state.
  <img src="https://github.com/vedantgoswami/SnakeGameAI/blob/main/Images/Model.svg">
* After executing the next state calculate the reward. Rewards are defined as below:
  1. Eat food  :  +10
  2. Game Over :  -10
  3. Else      :    0
* Update the Q value and Train the Model.

After analysing the algorithm now we have to build the idea to proceed for coding this algorithm.<br><br>
Our Project will be divided into three Modules named <b>Agent, Game and Model</b>
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
