---
title: 'Load-reduced Control of Launch Vehicle Based on Inverse Reinforcement Learning'
date: 2020-07-05
draft: false
tags: 
  - Inverse Reinforcement Learning
description: 'To avoid potential risk, the aerodynamic load must be relieved through attitude control. Current load relief schemes both have limitations, like low load reduction ratio and cannot adapt to changing environments. This project develops a load relief scheme via IRL (Inverse Reinforcement Learning) to achieve both high load reduction ratio and adaptivity on changing environments.'
---
## 1. Background
During the ascent phase, the launch vehicle has to suffer a huge aerodynamic load. If this load overweight structural limitation, it will be a disaster. To avoid potential risk, the aerodynamic load must be relieved through attitude control.
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/IRL/current.png?raw=true alt="image" caption="Current load relief scheme" class="big" >}}
Current load relief schemes both have limitations, like low load reduction ratio and cannot adapt to changing environments.

The motivation of this project is to design a new load relief scheme to achieve both high load reduction ratio and adaptivity on the real-time wind.

## 2. Challenge
The reinforcement learning method has environmental adaptability, but designing a reward function artificially is difficult. Because load relief is only part of the launch task, and there is no mathematical definition of “good ascent flight”.
Besides, the dynamics of the launch vehicle is highly dimensional, how to improve the load reduction ratio without affecting other functions of the vehicle control system is a problem.
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/IRL/Controlsystem.png?raw=true alt="image" caption="Trajectory phases" class="medium" >}}

## 3. GAIL load relief scheme
By analyzing each part of the control system, I designed the following GAIL Load relief scheme. 
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/IRL/GAIL.png?raw=true alt="image" caption="GAIL load relief scheme" class="medium" >}}

The traditional Guidance System is replaced by GAIL agent, as this section interacts with the environment directly. Since the reward function is hard to design, the passive scheme is introduced to give demonstrations, refer to this set as a criterion, generative adversarial imitation learning framework is used for training.

## 4. Results
This new scheme maintains aerodynamic load below 1000Pa in 64 different wind profiles. And performs more stable compared with the passive load relief method. 
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/IRL/Results1.png?raw=true alt="image" caption="Aerodynamic load in 64 different wind profiles" class="medium" >}}
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/IRL/Results2.png?raw=true alt="image" caption="Trajectory comparation with passive method" class="big" >}}
So this new scheme not only achieves both High load reduction ratio and Strong adaptivity, but also has stable performance.

## 5. Contribution
- Designed a load-reduced scheme, in which agent generate load-reduced trajectory learned from passive load-reduced control method (a current method in practice).
- Created a launch vehicle ascent phase training environment that has 24 different wind profiles for training.
- Achieved high proportion load reduction at 60%-70% and adaptability in 64 types of wind environment.
