# Parallelization of Dial-A-Ride Problem using Tabu-Search Heuristic

## Abstract

Dial A Ride is a transportation system to manage the transporation demands in a bounded geographic area. The demands typically include service requests to pickup and dropoff a customer from one point to another. The request comes with a pick-up time and dropoff time, the system guarantees a time windows by usually padding few minutes before and after these request times. Based on how and when the requests are received DAR is classified into two types, Static DAR and Dynamic DAR. In static DAR all the requests are known in advance, in dynamic DAR requests can come while the service is active. DAR is useful in demographic areas where the population is less dense or public transportation is weak.

The system guarantees request time windows, fleet size, customer ride time, service quality and optimized cost to run the system. DARP is NP-Hard and it is generalized from the Pick and Delivery Problem with Time Windows (PDPTW). Several extact, heuristic and GPU solutions have proposed in the past, this paper focuses on modelling the given problem to take advantage of multi-core CPU using Tabu Search Heuristic. The GPU while being much more capable of handling CPU intensive tasks, they are really expensive and it is also requires to tune the program code with every new iteration of the GPU architecture. This paper takes the approach of modelling the problem for the multi-core CPU and discusses the implemenation in Julia language and results.


## Introduction

Dial-A-Ride Problem (DARP) deals with moving passengers from one location to another while respecting the fleet size, passenger pikcup/dropoff time, service quality, ride time of passenger, ride quality and many other things. The main objective of the problem is to generate routes honoring all the constraints in the system. This paper deals with static DARP with fixed homogenous fleet, which means all the requests are known in advance, fleet size is fixed and all the vehicles on fleet have the same capacity. This comes down to solving a problem involving lot of constraints, which is also called Mixedd integer linear programming formulation.



