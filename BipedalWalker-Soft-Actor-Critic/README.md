# Project - BipedalWalker with Soft Actor-Critic (SAC)


### Introduction

Solving the environment require an average total reward of over 300 over 100 consecutive episodes.
Training of BipedalWalker is considered as [difficult task](https://ctmakro.github.io/site/on_learning/rl/bipedal.html), in particular, it is very difficult to train BipedalWalker by DDPG and PPO (with one agent). We solve the environment 
by usage of the __SAC__ algorithm, see the basic paper [SAC: Off-Policy Maximum Entropy Deep RL with a Stochastic Actor](https://arxiv.org/abs/1801.01290/). For another solution (based on the single agent) see 
[BipedalWalker-TD3](https://github.com/Rafael1s/Deep-Reinforcement-Learning-Algorithms/tree/master/BipedalWalker-TwinDelayed-DDPG%20(TD3)). 

![](images/bwalker_sac_08.png)

### Requirement

* [python 3.7](https://www.python.org) 
* [pytorch 1.0.1](https://pytorch.org/)
* [gym 0.13.1](https://github.com/openai/gym)
     
     
### Hyperparameters

Agent uses the following hyperparameters:

_gamma=0.99_ # discount    
_mini_batch=256_ # optimizer and backward mechisms work after sampling BATCH elements   
_lr = 0.0001_ # learning rate    
_eps=0.2_ # the clipping parameter using for calculation of the _action loss_   

### Entropy regularization

A central feature of SAC is [entropy regularization](https://spinningup.openai.com/en/latest/algorithms/sac.html).   
The major difference with common RL algorithms is training to maximize a trade-off between    
expected return and entropy, a measure of randomness in the policy. This has a close connection    
to the exploration-exploitation trade-off: increasing entropy results in more exploration,  
which can accelerate learning later on. It can also prevent the policy from prematurely    
converging to a bad local optimum.


### Off-policy

SAC is an **off-policy** algorithm. In other words, the SAC algorithm allows reusing the already collected data.
In the **agent.update_parameters** we get the batch of (_state, action, reward,  next_state, mask_)  of the _length = batch_size_:  



### Video

See video [Four BipedalWalker Gaits](https://www.youtube.com/watch?v=PFixqZEYKh4) demonsrating 
4 different BipedalWalker-walks related with 4 different sets of SAC-hyperparameters.






