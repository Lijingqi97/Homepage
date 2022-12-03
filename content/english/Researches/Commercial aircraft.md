---
title: 'Aircraft Autonomous Trajectory Generation (AATG)'
date: 2022-12-01
draft: false
tags: 
  - Commercial aircraft
  - Trajectory Planning
description: 'To establish the future autonomous air traffic management system, waypoint decisions must be integrated into trajectory planning to extend trajectory flexibility. However, designing an effective method for this problem is challenging as the synthesis of discrete decisions and continuous aircraft dynamics is NP-hard, besides, the complex and irregular layout of waypoints poses additional adaptivity performance for the method. This project focuses on the intercontinental long-range flight phase of commercial aircraft with route constraints and studies the waypoint decision autonomy in 4D trajectory planning based on intelligent methods. '
image: "images/CommercialAircraft/waypoint.jpg"
---
In the future, the aircraft trajectory will be co-determined by the commercial aircraft and air traffic management system in the concept of Four-Dimensional Trajectory-Based Operation (4D-TBO). Flight safety is crucial for aviation activities, and the commercial aircraft trajectory must pass through waypoints so that the whole flight is supervised by ground facilities.

Therefore, to establish the future autonomous air traffic management system, waypoint decisions must be integrated into trajectory planning to extend trajectory flexibility. However, designing an effective method for this problem is challenging as the synthesis of discrete decisions and continuous aircraft dynamics is NP-hard, besides, the complex and irregular layout of waypoints poses additional adaptivity performance for the method. 
![Build status](https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/CommercialAircraft/trajPhase.png?raw=true)

This project focuses on the intercontinental long-range flight phase of commercial aircraft with route constraints and studies the waypoint decision autonomy in 4D trajectory planning based on intelligent methods. Considering the different phases of the trajectory, this project can be saperate into two parts:
- The first one aims to reference trajectory before the flight. 
- The second one aims to the operation trajectory during the in-flight phase.

## Part1: Effective Mixed-Integer Trajectory Planning Approach for Large Aircraft

### 1. Challenge
Typically, aircraft trajectory planning is formulated as an optimal control problem. However, the feature of aircraft dynamics makes the problem highly non-convexity. And introducing isolated waypoint decisions poses a Mixed-integer optimal control problem, this problem is hard to solve effectively because of following reasons:
- **Continuity:** Differential format of aircraft dynamics.
- **Non-convexity:** Highly coupled dynamics of aircraft.
- **NP-hard:** Include waypoint decision.

Even though heuristic branch-and-bound method is a possible way to solve it, this method relies on the artificially designed near-optimal trajectory, leading to full-automatic performance hard to achieve.

### 2. Iterative Convex Mixed-Integer Method
An Iterative Convex Mixed-integer method is proposed, whose procedure is illustrated below. Using linearization and discretization, the original problem is formulated as a mixed-linear planning problem at reference trajectory, then the final solution can be approached iteratively. 
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/CommercialAircraft/ICMI.png?raw=true alt="image" caption="ICMI procedure" class="small" >}}

### 3. Results
The iterative process overcomes the dependence on near-optimal guesses. And improve solve time to 300 seconds. This figure illustrates the iteration process, we can see that the trajectory in different iterations passes through the same waypoints sequence.
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/CommercialAircraft/resultICMI.png?raw=true alt="image" caption="Trajectories during the iterations" class="big" >}}

### 4. Contribution
- Established a mixed-integer optimal control model to describe trajectory planning problem of
large aircraft with waypoint selection considered.
- Developed an efficient iterative method that computes sub-problem of mixed-integer linear
planning in each iteration.
- Achieved rapid trajectory planning with within 5 minutes given a wind forecast.

## Part2: Online Aircraft Trajectory Re-planning Approach with Waypoint Decision

### 1. Challenge
As for the tactical online phase, like weather avoidence scenarios, the aircraft only has seconds to generate a trajectory, which means the method must be near real-time. The ICMI method cannot satisfy this performance requirement as solve hybrid variables together has computational burden. Introducing learning-based method for decision is possible to accelerate the solving process by separating different variables. However, in this waypoint decision problem, how to utilize the two-dimensional information behind the waypoint, and create a decision neural network that has adaptability is challenging.
- **Real-time performance**
- **Waypoints information is two-dimensinal**
- **Adaptability performance**

### 2. Decision-Generation Method
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/CommercialAircraft/DGM.png?raw=true alt="image" caption="DGM procedure" class="medium" >}} 

In this method, the strategy network is innovative.

{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/CommercialAircraft/transfer.png?raw=true alt="image" caption="Design Strategy Network" class="big" >}}

### Contribution
- Established a bi-layer model in which waypoint decision process is formulated as a sequential
classifying problem.
- Proposed a bi-layer decision-generation method, in which a small-scaled neural network is designed for waypoint decision, and trajectory is generated via iterative method underlying settled
waypoints.
- Improved the speed of waypoint decision-trajectory planning of large aircraft to 3 seconds.
- Achieved re-planning aircraft trajectory on different irregular waypoint layouts.