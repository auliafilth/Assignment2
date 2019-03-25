# Assignment2: Learning and Control for Dynamics

## Objective

To provide practice implementing simple learning and control methods on one of the most common example systems.

## Getting started with the provided code 

- Ensure that you have installed python, numpy matplotlib and scipy
- Run the provided example with `python cartpole_learn.py`
  - A GUI window should appear showing the carpole falling over
  - The code should print the error per episode to terminal standard output
- Enter ctrl+c to stop the process

## How to interact with this system using your own code

You only have to add code to one file: src/cartpole_learn.py. Except for parameter changes to the simulator that you might try, all the code can be placed in the policyfn method.

- This method takes x, the state of the cartpole which is expressed in 5 dimensions:
  - The cart position, x, in x[0]
  - The cart linear velocity, x_dot, in x[1]
  - The cart angular velocity, theta_dot, in x[2]
  - The sin of the cart's angle, sin(theta), in x[3]
  - The cos of the cart's angle, cos(theta), in x[4]
- We use the cos/sin representation to prevent problems with angle wrap-around
  
## Aims for your code:

1. Implement well-tuned PID control to stabilize the pendulum at the top
  1. Try both manual gain search and Ziegler-Nicols. Could you find K ultimate?
  2. The code computes a sum_of_error each episode. This can provide feedback for a more adaptive gain tuning algorithm. Implement twiddle, or another learning approach of your choice to find gains that beat your hand-tuned choices.
2. Connect the system to an LQR library that solves for the approximately optimal balancing controller near the goal. (Does LQR beat your hand-tuned PID?) 
3. Implement dynamics model learning to be able to predict the outcome of a series of actions over time.

## Hints and Information:

Line 38 of cartpole.py controls the initial state. Change the 4th value to 0 in order to try the swing-up task, or add random sampling to have it start from a different spot in each episode.

