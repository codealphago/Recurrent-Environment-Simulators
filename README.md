# Recurrent-Environment-Simulators
Modeling the environment is an important task for intelligent agents to be able to plan and act efficiently. A Recurrent Environment Simulator network can achive this task easily by learning to predict the next observation given the history of observations and actions. Making the agent able to predict the consequences of its actions.

This repository contains a tensorflow implementation of the Recurrent Enviroment Simulators paper puplished by DeepMind at ICML 2017. (https://arxiv.org/abs/1704.02254)







## Network Architecture 
The following figure visualize the RES architecture. It can be devided to three main parts, the encoder, the decoder and the action-conditioned LSTM. The encoder extract the features from the observation at time step ```t```, the action-conditioned LSTM keeps useful features from previous frames to help the decoder predict better observations for time step ```t+1```.

<div align="center">
<img src="imgs/3.png"><br><br>
</div>


# Action-conditioned LSTM
One of the main contributions of their work is fusing the action with the hidden state representation when predicting the next hidden state representation in time. In previous work, the action was used instead to directly predict the next image. Why? Authors suggest it could “enable the model to incorporate action information more effectively”.
so paper used a modified version of LSTM called Action conditioned LSTM.
mainly it's an early fusion between actions and states. They used this approach as it enables them to explore how the model generalises to different action policies.


<div align="center"> 
<img hight="1000" width="1000" src="imgs/1.png"><br><br>
</div>

# Data Collection using A2C RL agent
We trained a synchronous Advantage Actor Critic (A2C) agent and used it to explore the desired enviroment and collect data, using openAi Atari enviroments.

We'll provide some collected data from different Atari enviroments.

# Usage
  ### Dependencies
```
Python 3.X
tensorflow 1.3.0
numpy 1.13.1
tqdm
```

### Run

- Collect data from any atari enviroment using the method mentioned before, or use the provided data.
- Edit the configration file to meet your need.
- Run ```python res.py is_train=True```


# License
This project is licensed under the Apache License 2.0 - see the LICENSE file for details.