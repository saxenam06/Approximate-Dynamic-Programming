A model based Reinforcement Learning algorithm which trains two Actor-Critic NNs that efficiently compute Optimal Steering control actions for following any path. To Validate the optimality of the trained parameterized control policy, the Actor NN's solution is compared with that provided by MPC(IPOPT) for the corresponding Optimal Control Problem.

As compared to the original code, the objective function of both Actor-Critic NNs and MPC are kept exactly same and the NNs are retrained while adapting learning rates.
Following results were achieved which clearly shows improvement as compared to the baseline results obtained from the trained network already provided in the original repository. The baseline results shows oscillatory response in both heading angle error and steering action which is not present in the optimal solution provided by MPC thus questioning the optimality of the previously provided trained NNs. With the retrained NNs the oscillatory behavior is almost eliminated and both the heading angle & steering response is very close to the optimal solution provided by MPC. This validates that the retrained NNs provides optimal solution to the corresponding OCP.

The retrained network is in [directory](https://github.com/saxenam06/Approximate-Dynamic-Programming/tree/demo/retrained_network/2021-12-27-13-49-10000).

Many Thanks to Haitong Ma for opensourcing the below respository which helped me to understand ADP & Actor-Critic MBRL.

![image](https://user-images.githubusercontent.com/83720464/147490157-2f2064dd-e846-486f-9294-09302c55e1ea.png)



# This is a modified version of the  [original](https://github.com/mahaitongdae/Approximate-Dynamic-Programming) respository. 

# Below contents from the  [original](https://github.com/mahaitongdae/Approximate-Dynamic-Programming) repository

# Vehicle Tracking Control

- Code demo for Chpater 8, Reinforcement Learning and Control.

- Methods: Approximate Dynamic Programming, Model Predictive Control

<div align=center>
<img src="utils/road.png" width = 50%/>
</div>

## Requirements

[PyTorch](https://pytorch.org/get-started/previous-versions/)  1.4.0

[CasADi](https://web.casadi.org/get/)


## Getting Started

- To train an agent, follow the example code in `main.py` and tune the parameters. Change `METHODS` variable for adjusting the methods to compare in simulation stage.
- Simulations will automatically executed after the training is finished. To separately start a simulation from a trained results and compare the performance between ADP and MPC, run `simulation.py`. Change `LOG_DIR` variable to set the loaded results.

## Directory Structure

```
Approximate-Dynamic-Programming
│  main.py - Main script
│  plot.py - To plot comparison between ADP and MPC
│  train.py - To execute PEV and PIM
│  dynamics.py - Vehicle model
│  network.py - Network structure
│  solver.py - Solvers for MPC using CasADi
│  config.py - Configurations about training and vehicle model
│  simulation.py - Run experiment to compare ADP and MPC
│  readme.md
│  requirements.txt
│
├─Results_dir - store trained results
│     
└─Simulation_dir - store simulation data and plots

```
## Related Books and Papers
[Reinforcement Learning and Control. Tsinghua University
Lecture Notes, 2020.](http://www.idlab-tsinghua.com/thulab/labweb/publications.html?typeId=3&_types)

[CasADi: a software framework for nonlinear optimization and optimal control](https://link.springer.com/article/10.1007/s12532-018-0139-4)



