# learn_cnn_encoded_propositions

This work is based on the paper: Learning CNN-Encoded Propositions for Robotic Programming from Few Demonstrations.

---

## Requirements
Ubuntu 18.04

ROS Melodic

Pytorch 1.7

Flask

[rosplan_demos](https://github.com/LCEPRPFD/rosplan_demos)

---

## Installation

The code has been tested with python3.8, CUDA 11 on Ubuntu18.

1. Follow the installation instructions in [rosplan_demos](https://github.com/LCEPRPFD/rosplan_demos) repository. 

2. Download learn_cnn_encoded_propositions repository.

```
git clone https://github.com/LCEPRPFD/learn_cnn_encoded_propositions.git
```
---

## Run

1. Use data [traj_demonstration](https://1drv.ms/u/s!An_sqEOHEaVaalbqMgGmadqPvqI?e=6wKFlF) and [train_symprop_maml.ipynb](/symbolic_proposition/train_symprop_maml.ipynb) to generate a data set including 10 demonstrations.

2. Start the flask service for proposition evaluation. A model finetuned by 10 demonstrations is used.

```
cd test
export FLASK_APP=symprop_app_10shot.py
flask run
```

3. Start Gazebo and ROSPlan framework.

    NOTE: The demo requires 2 terminals.
     
   1. In the first terminal, begin the simulation, rviz visualisation, and ROSPlan nodes using the `demo.launch` from the `rosplan_demo` package:

    ```
    cd rosplan_ws
    source devel/setup.bash
    roslaunch rosplan_demo demo.launch
    ```

   2. In a second terminal run `demo.bash`, a script which:
    - Add to the knowledge base the PDDL objects and facts which comprise the initial state.
    - Add the goals to the knowledge base.
    - Call the ROSPlan services which generate a plan and dispatch it.

    ```
    cd rosplan_ws
    source devel/setup.bash
    rosrun rosplan_demo demo.bash
    ```
