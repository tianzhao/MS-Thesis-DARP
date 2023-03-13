## Abstract

Dial A Ride is a transportation system to manage the transporation demands in a bounded geographic area. The demands typically include service requests to pickup and dropoff a customer from one point to another. The request comes with a pick-up time and dropoff time, the system guarantees a time windows by usually padding few minutes before and after these request times. Based on how and when the requests are received DAR is classified into two types, Static DAR and Dynamic DAR. In static DAR all the requests are known in advance, in dynamic DAR requests can come while the service is active. DAR is useful in demographic areas where the population is less dense or public transportation is weak.f

The system guarantees request time windows, fleet size, customer ride time, service quality and optimized cost to run the system. DARP is NP-Hard and it is generalized from the Pick and Delivery Problem with Time Windows (PDPTW). Several extact, heuristic and GPU solutions have proposed in the past, this paper focuses on modelling the given problem to take advantage of multi-core CPU using Tabu Search Heuristic. The GPU while being much more capable of handling CPU intensive tasks, they are really expensive and it is also requires to tune the program code with every new iteration of the GPU architecture. This paper takes the approach of modelling the problem for the multi-core CPU using Tabu-Search Heuristic, presents a implemenation in Julia language and discusses the results on various multi-core configuations.

# Abstract 2

Dial A Ride (DAR) is a transportation system to manage and meet the transportation demands in a bounded geographic area with a fleet of vehicles. Dial A Ride Problem (DARP) is to generate a solution for DAR with optimal scheduling and routing that satisfies the constraints of DAR such as pickup/dropdown time windows, fleet capacity, and rider satisfactions. This can be classified as a Mixed Integer Programming formulation or combinatorics optimization problem. DAR can be useful in designing or planning solutions such as para-transit and community ride scheduling. Various exact solution have been proposed in the past, but none of them are viable for the real world runtime requirements and computational costs. Therefore, meta-heuristics were employed to solve DARP such as tabu search, variable neighbood search, deterministic annealing, and multi-atomic annealing. Recent research projects have utilized high-performance architectures such as GPU and computing clusters to implement these meta-heuristics algorithms. However, the cost of access to GPUs and computing clusters as well as their ever-evolving architectures make it difficult to apply DARP solutions that require architecture-specific optimizations.  

This paper studies the DARP algorithm using Tabu Search heuristic and feasibility of CPU-based parallel solution with shared memory. The rationale for using CPU based parallelism with shared memory is because of its extensive availability in the everyday machines than it is in the past. With targeting the multi-core CPU we can have the implementation portable and also get the CPU level optimizations offered by compilers. This paper uses the variant of algorithm proposed for GPU here[1], but it is adapted for multi-core CPU with shared memory. The implementation is done in Julia and the tests are performed on local and cloud machines with different multi-cores configurations. [[Details about performance comparisions]]

## Introduction

Dial-A-Ride Problem (DARP) deals with moving passengers from one location to another while respecting the fleet size, passenger pikcup/dropoff time, service quality, ride time of passenger, ride quality and many other things. The main objective of the problem is to generate routes honoring all the constraints in the system. Based on how the requests are received, the DAR can be classified into two categories, Static DAR and Dynamic DAR. In static DAR all the requests are known in advance, in dynamic DAR requests can come even when the service is active. This paper deals with static DARP with fixed homogenous fleet, which means all the requests are known in advance, fleet size is fixed and all the vehicles on fleet have the same capacity. Various exact solutions have been proposed in the past that solves the DARP optimally, but the blocker for adapting these in read-world are execution time and computational costs. The Greedy solutions cannot escape the local optima to reach the global optima. Therefore, we need to allow the optimization function to deteriorate, so that local optima is escaped. So, many meta-heuristics are used to solve DARP such as tabu search, variable neighbood search, deterministic annealing, and multi-atomic annealing. While meta-heuristics doesn't result the global optima, they generally result in near-optimal results, which were good enough in the read world scenarios. With the advent of robo taxis, the scale of the problem is only going to increase. Therefore it is really essential to develop methodologies that can quickly generate good enough solution using less computational resourses.

This paper uses Granular Tabu-Search heuristic algorithm, Tabu Search is meta-heuristic approach designed to provide a sufficiently good solution to an optimization problem. It doesn't guarantee that global optimal solution can be found. Granular Tabu Search is Tabu Seach with particular focus on the local search phrase. The algorithm searches for the next move in a set of possible moves, which is called neighborhood. Granular neighborhood is reduced set of possible moves. A GPU algorithm has been proposed for the Granular Tabu Search algorithm for DARP. This paper uses algorithm proposed in here[], but models it to the multi-core CPU architectures using parallel programming semantics in julia language.

### Formulation

### About Tabu Search

Granular Tabu Search is a meta-heuristic, which focuses on search phase. For tabu search, we first need to form or generate a initial soliution. Once the initial solution is generated and optimization value for this solution calculated, we can start the local search phase of the algorithm. Using the initial solution, the algorithm finds all the valid moves that can be made so that the much better solution can be formedf. A move can be a change or modification to the solution that results in a new solution. Local search phase is then defined as finding or searching for the best move possible at each iteration which results in a new solution and using the new solution as base solution to search for the best possible move and so on. At

## Issues with using assignment problem

### Issues with GPU solutions

### Modelling Tabu Search for multi core

### Implemenation

### Results and biblography



