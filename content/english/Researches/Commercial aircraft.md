---
title: 'Intelligent Method for Aircraft Autonomous Trajectory Generation'
date: 2022-10-01
draft: false
tags: 
  - Commercial aircraft
  - Trajectory Planning
description: 'To establish the future autonomous air traffic management system, waypoint decisions must be integrated into trajectory planning to extend trajectory flexibility. However, designing an effective method for this problem is challenging as the synthesis of discrete decisions and continuous aircraft dynamics is NP-hard, besides, the complex and irregular layout of waypoints poses additional adaptivity performance for the method. This project focuses on the intercontinental long-range flight phase of commercial aircraft with route constraints and studies the waypoint decision autonomy in 4D trajectory planning based on intelligent methods. '
---

In the future, the aircraft trajectory will be co-determined by the commercial aircraft and air traffic management system in the concept of Four-Dimensional Trajectory-Based Operation (4D-TBO). Flight safety is crucial for aviation activities, and the commercial aircraft trajectory must pass through waypoints so that the whole flight is supervised by ground facilities.

Therefore, to establish the future autonomous air traffic management system, waypoint decisions must be integrated into trajectory planning to extend trajectory flexibility. However, designing an effective method for this problem is challenging as the synthesis of discrete decisions and continuous aircraft dynamics is NP-hard, besides, the complex and irregular layout of waypoints poses additional adaptivity performance for the method. 

This project focuses on the intercontinental long-range flight phase of commercial aircraft with route constraints and studies the waypoint decision autonomy in 4D trajectory planning based on intelligent methods. Considering the different phases of the trajectory, this project can be saperate into two parts. The first one aims to reference trajectory before the flight, and the second one aims to the operation trajectory during the in-flight phase.

## Effective Mixed-Integer Trajectory Planning Approach for Large Aircraft
- Established a mixed-integer optimal control model to describe trajectory planning problem of
large aircraft with waypoint selection considered.
- Developed an efficient iterative method that computes sub-problem of mixed-integer linear
planning in each iteration.
- Achieved rapid trajectory planning with within 5 minutes given a wind forecast.

## Online Aircraft Trajectory Re-planning Approach with Waypoint Decision
- Established a bi-layer model in which waypoint decision process is formulated as a sequential
classifying problem.
- Proposed a bi-layer decision-generation method, in which a small-scaled neural network is designed for waypoint decision, and trajectory is generated via iterative method underlying settled
waypoints.
- Improved the speed of waypoint decision-trajectory planning of large aircraft to 3 seconds.
- Achieved re-planning aircraft trajectory on different irregular waypoint layouts.