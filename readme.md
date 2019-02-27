## ICRA

## 2018

### Deep Reinforcement Learning for Vision-Based Robotic Grasping:A Simulated Comparative Evaluation of Off-Policy Methods

environment:openAI Gym

simulator:Bullet  7自由度机械臂，从箱子中抓取物体

reward 设置在最后一步，抓起来就是1抓不起来就是0

off-policy比on-policy在抓取上更受欢迎，因为它不需要让机器人重复访问之前看到的东西以避免遗忘

本篇论文的目的是寻找最适合基于视觉的抓取的强化学习的算法，强调多样性和泛化能力。

验证了supervised learning,DQN,DDPG,MC,Corr MC,PCL等多种算法。

deep RL能成功学习并抓取没有见过的物体，平均成功率达90%，蒙特卡罗算法和DQN也表现出色。

Policy Gradient基于概率

Value-based基于值

Actor-critic两者之间



常规训练：900个训练集，多次训练抓取；

​		    100个测试集，之前从来没有见过。

目标训练：7个物体中有3个有target标签，只有抓了这三个才有奖励。

| algorithm             | target value            | action selection  |
| --------------------- | ----------------------- | ----------------- |
| supervised learning   | episode value           | stochastic search |
| Q-learning            | bootstrapped            | stochastic search |
| Monte Carlo           | episode value           | stochastic search |
| corrected Monte Carlo | corrected episode value | stochastic search |
| DDPG                  | bootstrapped            | actor network     |
| PCL                   | corrected episode value | actor network     |
|                       |                         |                   |

四个评估的指标：

综合表现，效率，鲁棒性，灵敏度

效率和准确率上，DQL,MC,corrected MC,supervised learning表现较好，DDPG和PCL表现较差。

鲁棒性上，corr MC,DQL,PCL较好，supervised和MC也还行，DDPG比较差。

数据不多的时候还是DQL好用

