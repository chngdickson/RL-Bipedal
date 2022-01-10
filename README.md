### Introduction

Training BipedalWalker is considered a [difficult task](https://ctmakro.github.io/site/on_learning/rl/bipedal.html, it is very difficult to train BipedalWalker by SAC, DDPG, PPO, TD3 (with one agent). It is simply easier to solve it using multiple environments.

This github is simply for comparing algorithms to be used in another project, [training_spot](https://github.com/chngdickson/training_spot). This environment will be much harder to run as I still currently unable to create a vectorized environment using webots.

DDPG was not considered as it is the same concept as SAC but slower. Hence, only SAC and PPO is considered.

![](BipedalWalker-PPO-VectorizedEnv/images/bwalker.png)

### Results
Out of SAC and PPO, SAC showed the most promise. With an average score of **300** at **400 episodes**. while PPO only reached a score of **300** at **450 episodes**.
I have yet to test out discrete delta PPO. But for now am satisfied with just these results.
