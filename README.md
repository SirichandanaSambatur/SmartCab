# Train a Smartcab to Drive
In this project, reinforcement learning techniques are applied for a self-driving agent in a simplified
world to aid it in effectively reaching its destinations in the allotted time. The Q-Learning algorithm is used for best configuration
of learning and exploration factors to ensure the self-driving agent is reaching its destinations with consistently positive 
results.

## Definitions

### Environment
The *smartcab* operates in an ideal, grid-like city (similar to New York City), with roads going in the North-South and East-West directions. Other vehicles will certainly be present on the road, but there will be no pedestrians to be concerned with. At each intersection there is a traffic light that either allows traffic in the North-South direction or the East-West direction. U.S. Right-of-Way rules apply: 
- On a green light, a left turn is permitted if there is no oncoming traffic making a right turn or coming straight through the intersection.
- On a red light, a right turn is permitted if no oncoming traffic is approaching from your left through the intersection.
To understand how to correctly yield to oncoming traffic when turning left, you may refer to [this official drivers? education video](https://www.youtube.com/watch?v=TW0Eq2Q-9Ac), or [this passionate exposition](https://www.youtube.com/watch?v=0EdkxI6NeuA).

### Inputs and Outputs
Assume that the *smartcab* is assigned a route plan based on the passengers? starting location and destination. The route is split at each intersection into waypoints, and you may assume that the *smartcab*, at any instant, is at some intersection in the world. Therefore, the next waypoint to the destination, assuming the destination has not already been reached, is one intersection away in one direction (North, South, East, or West). The *smartcab* has only an egocentric view of the intersection it is at: It can determine the state of the traffic light for its direction of movement, and whether there is a vehicle at the intersection for each of the oncoming directions. For each action, the *smartcab* may either idle at the intersection, or drive to the next intersection to the left, right, or ahead of it. Finally, each trip has a time to reach the destination which decreases for each action taken (the passengers want to get there quickly).  If the allotted time becomes zero before reaching the destination, the trip has failed.

### Rewards and Goal
The *smartcab* will receive positive or negative rewards based on the action it as taken. Expectedly, the *smartcab* will receive a small positive reward when making a good action, and a varying amount of negative reward dependent on the severity of the traffic violation it would have committed. Based on the rewards and penalties the *smartcab* receives, the self-driving agent implementation should learn an optimal policy for driving on the city roads while obeying traffic rules, avoiding accidents, and reaching passengers? destinations in the allotted time.


This project contains three directories:

- `/logs/`: This folder will contain all log files that are given from the simulation when specific prerequisites are met.
- `/images/`: This folder contains various images of cars to be used in the graphical user interface. 
- `/smartcab/`: This folder contains the Python scripts that create the environment, graphical user interface, the simulation, and the agents. 

It also contains two files:
- `smartcab.ipynb`: This is the main file where various questions related to project have been answered and detailed analysis of the project.
-`visuals.py`: This Python script provides supplementary visualizations for the analysis.

Finally, in `/smartcab/` are the following four files:
- `agent.py`: This is the main Python file where the agent is created and Q-learning algorithm is implemented.
- `environment.py`: This Python file will create the *smartcab* environment. 
- `planner.py`: This Python file creates a high-level planner for the agent to follow towards a set goal.
- `simulation.py`: This Python file creates the simulation and graphical user interface. 

## Software Requirements
This project uses the following software and Python libraries:

- [Python 2.7](https://www.python.org/download/releases/2.7/)
- [NumPy](http://www.numpy.org/)
- [pandas](http://pandas.pydata.org/)
- [matplotlib](http://matplotlib.org/)
- [PyGame](http://pygame.org/)

## Running the Code
In a terminal or command window, navigate to the top-level project directory `smartcab/` (that contains the two project directories) and run one of the following commands:

`python smartcab/agent.py` or  
`python -m smartcab.agent`
