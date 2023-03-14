## Abstract

Dial A Ride (DAR) is a transportation system to manage transportation demands in a bounded geographic area using a fleet of vehicles. It can be defined as set of customers requesting transporation service from one to another with set of constraints like pickup/dropoff locations and time-windows. Thus, Dial-A-Ride problem can be defined as generating a schedule or routes for vehicles in DAR such that it is optimized for various parameters, such as cost of service, quality of service, service in defined time windows and so on. The DARP can be useful for many real-world use cases such as community transport planning, para-transportation and meeting transporation needs where the population is sparse or weak. It is proved to be NP-Hard and thus very computationally intensive. Therefore it requires a lot of computational power to solve at scale. Many exact solutions have been proposed in the past, but none of them have viable execution time for real-world scale. Current state of art of solutions are using meta-heuristics such as tabu search, variable neighbood search, deterministic annealing, multi-atomic annealing. GPU's are also employed to take advantage of High Performance computing. While GPU's offer great computing power, they are very expensive and require low-level program and architecture specific optimizations. Massive parallel machines are hard to get hands on, so they are not viable too.

This paper takes a rather practical approach of using highly avaiable, less expensive multi-core CPU machines to solve DARP. The rationale behind using multi-core CPU machines is that, they have now become common in everyday machines, they are less expensive, easy to get hands on and does not require low level program and architecture specific optimization, thanks to modern compilers. This paper uses Granual Tabu Search algorithm proposed for GPU[1]. Unlike traditional tabu search algorithms, this paper uses a method of large random solutions to generate a initial solution. The algorithm discussed in this paper is implemented in Julia and benchmarking is done on various configuration of DARP dataset on different thread configurations using local and cloud machines with high number of CPU cores.



### Introduction
### Formulation

### About Tabu Search

Granular Tabu Search is a meta-heuristic, which focuses on search phase. For tabu search, we first need to form or generate a initial soliution. Once the initial solution is generated and optimization value for this solution calculated, we can start the local search phase of the algorithm. Using the initial solution, the algorithm finds all the valid moves that can be made so that the much better solution can be formedf. A move can be a change or modification to the solution that results in a new solution. Local search phase is then defined as finding or searching for the best move possible at each iteration which results in a new solution and using the new solution as base solution to search for the best possible move and so on. At

## Issues with using assignment problem

### Issues with GPU solutions

### Modelling Tabu Search for multi core

### Implemenation

### Results and biblography



