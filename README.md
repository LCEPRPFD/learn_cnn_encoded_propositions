# learn_cnn_encoded_propositions

---

## Requirements
Ubuntu 18.04
Python 2.7

---

## Run

NOTE: The demo requires 2 terminals.

Baseline demo:
*1.*In the first terminal, begin the simulation, rviz visualisation, and ROSPlan nodes using the `demo.launch` from the `rosplan_demo` package:
```
roslaunch rosplan_demo demo.launch
```
*2.*In a second terminal run `demo.bash`, a script which:
- adds to the knowledge base the PDDL objects and facts which comprise the initial state.
- adds the goals to the knowledge base.
- calls the ROSPlan services which generate a plan and dispatch it.
```
rosrun rosplan_demo demo.bash
```

Demonstrations demo:
*1.*In the first terminal, begin the simulation, rviz visualisation, and ROSPlan nodes using the `demo_baseline.launch` from the `rosplan_demo` package:
```
roslaunch rosplan_demo demo_baseline.launch
```
*2.*In a second terminal run `demo.bash`, a script which:
- adds to the knowledge base the PDDL objects and facts which comprise the initial state.
- adds the goals to the knowledge base.
- calls the ROSPlan services which generate a plan and dispatch it.
```
rosrun rosplan_demo demo.bash
```