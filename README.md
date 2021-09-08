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

2. Download learn_cnn_encoded_propositions repository

```
git clone https://github.com/LCEPRPFD/learn_cnn_encoded_propositions.git
```

---

## Run

1. Start the flask service for proposition evaluation. A model finetuned by 10 demonstration is used for proposition evaluation.

```
cd test
export FLASK_APP=symprop_app_10shot.py
flask run
```

2. Start Gazebo and ROSPlan framework.

    NOTE: The demo requires 2 terminals.
     
   1. In the first terminal, begin the simulation, rviz visualisation, and ROSPlan nodes using the `demo.launch` from the `rosplan_demo` package:

    ```
    cd rosplan_ws
    source devel/setup.bash
    roslaunch rosplan_demo demo.launch
    ```

   2. In a second terminal run `demo.bash`, a script which:
    - adds to the knowledge base the PDDL objects and facts which comprise the initial state.
    - adds the goals to the knowledge base.
    - calls the ROSPlan services which generate a plan and dispatch it.

    ```
    cd rosplan_ws
    source devel/setup.bash
    rosrun rosplan_demo demo.bash
    ```
