---
author: Jingqi LI
title: AATG Part 1
date: 2022-11-01
description: Method for reference trajectory before the flight
series:
  - Aircraft Autonomous Trajectory Generation
---

# Effective Mixed-Integer Trajectory Planning Approach for Large Aircraft

## 1. Challenge
Typically, aircraft trajectory planning is formulated as an optimal control problem. However, the feature of aircraft dynamics makes the problem highly non-convexity. And introducing isolated waypoint decisions poses a Mixed-integer optimal control problem, this problem is hard to solve effectively because of following reasons:
- **Continuity:** Differential format of aircraft dynamics.
- **Non-convexity:** Highly coupled dynamics of aircraft.
- **NP-hard:** Include waypoint decision.

Even though heuristic branch-and-bound method is a possible way to solve it, this method relies on the artificially designed near-optimal trajectory, leading to full-automatic performance hard to achieve.

## 2. Iterative Convex Mixed-Integer Method
An Iterative Convex Mixed-integer method is proposed, whose procedure is illustrated below. Using linearization and discretization, the original problem is formulated as a mixed-linear planning problem at reference trajectory, then the final solution can be approached iteratively. 
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/CommercialAircraft/ICMI.png?raw=true alt="image" caption="ICMI procedure" class="small" >}}

## 3. Results
The iterative process overcomes the dependence on near-optimal guesses. And improve solve time to 300 seconds. This figure illustrates the iteration process, we can see that the trajectory in different iterations passes through the same waypoints sequence.
{{< figure src=https://github.com/Lijingqi97/JingqiLI_Homepage/blob/main/static/images/CommercialAircraft/resultICMI.png?raw=true alt="image" caption="Trajectories during the iterations" class="big" >}}

## 4. Contribution
- Established a mixed-integer optimal control model to describe trajectory planning problem of
large aircraft with waypoint selection considered.
- Developed an efficient iterative method that computes sub-problem of mixed-integer linear
planning in each iteration.
- Achieved rapid trajectory planning with within 5 minutes given a wind forecast.

## *Related works of this project:*