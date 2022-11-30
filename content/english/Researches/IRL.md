---
title: 'Load-reduced Control of Launch Vehicle Based on Inverse Reinforcement Learning'
date: 2020-07-05
draft: false
tags: 
  - Inverse Reinforcement Learning
description: 'To avoid potential risk, the aerodynamic load must be relieved through attitude control. Current load relief schemes both have limitations, like low load reduction ratio and cannot adapt to changing environments. This project develops a load relief scheme via IRL (Inverse Reinforcement Learning) to achieve both high load reduction ratio and adaptivity on changing environments.'
---

- Designed a load-reduced scheme, in which agent generate load-reduced trajectory learned from passive load-reduced control method (a current method in practice).
- Created a launch vehicle ascent phase training environment that has 24 different wind profiles for training.
- Achieved high proportion load reduction at 60%-70% and adaptability in 64 types of wind environment.