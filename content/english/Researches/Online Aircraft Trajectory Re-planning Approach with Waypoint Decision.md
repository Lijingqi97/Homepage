---
author: Jingqi LI
title: AATG Part 2 
date: 2022-10-01
description: Method for operation trajectory during the flight
series:
  - Aircraft Autonomous Trajectory Generation
---

## Online Aircraft Trajectory Re-planning Approach with Waypoint Decision

## 1. Challenge
As for the tactical online phase, like weather avoidence scenarios, the aircraft only has seconds to generate a trajectory, which means the method must be near real-time. The ICMI method cannot satisfy this performance requirement as solve hybrid variables together has computational burden. Introducing learning-based method for decision is possible to accelerate the solving process by separating different variables. However, in this waypoint decision problem, how to utilize the two-dimensional information behind the waypoint, and create a decision neural network that has adaptability is challenging.
- **Real-time performance**
- **Waypoints information is two-dimensinal**
- **Adaptability performance**

## 2. Decision-Generation Method
{{< figure src="/images/CommercialAircraft/DGM.png" alt="image" caption="DGM procedure" class="medium" >}}

In this method, the strategy network is innovative.
{{< figure src="/images/CommercialAircraft/transfer.png" alt="image" caption="Design Strategy Network" class="big" >}}

## Contribution
- Established a bi-layer model in which waypoint decision process is formulated as a sequential
classifying problem.
- Proposed a bi-layer decision-generation method, in which a small-scaled neural network is designed for waypoint decision, and trajectory is generated via iterative method underlying settled
waypoints.
- Improved the speed of waypoint decision-trajectory planning of large aircraft to 3 seconds.
- Achieved re-planning aircraft trajectory on different irregular waypoint layouts.

## *Related works of this project:*