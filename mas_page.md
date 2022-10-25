## Multi-Agent System project: the packet world

**Project description:**  [This](https://people.cs.kuleuven.be/~danny.weyns/events/MASE/group_22.pdf) was the project for the course on Multi-Agent System during my master degree

### 1. Context

A MAS is a software system that instantiates ”agents” evolving in an environment and which interact and work together in order to accomplish a goal that they could not reach without group cooperation. These decentralized software systems allow for more flexibility to deal with complex and dynamic environments.

The goal of this course project was to explore various paradigms of MAS in a testbed called the Packet-World, which consist of a 2D grid where each position (square) can be either filled with an object, or an agent (or be empty). The agents have to collect colored packets and bring them to the matching colored destination.

<p align="center">
<img src="images/task-mas.png?raw=true" width="40%" height=auto />
</p>

### 2. Problem

For a MAS to work, several problems have to be taken care of:

- _Autonomous behaviour of the agents_, i.e. in the simplest scenario, an agent has to be able to pick up a packet and load it at destination
- _Coordination of agents to manage their energy_ : sources of energy are limited and agents must cooperate to access them when they need to
- _Task delegation to go over constraints_ : as shown in the screenshot above, sometines agents must cooperate to help each other accomplish their task (indeed only same colored agent can move a blocking cube).

### 3. Solutions

For each of the problems introduced above, we designed a solution that we instanciated in one of the "World" at our disposal (the code for the visual part was already developed, we had to modified some classes mainly concerning the agent behaviour).

For instance, for the task delegation problem we coded a "gradient" that agents can generate to communicate the other agents that a packet need to be remove, you can see this in action below.

<p align="center">
<img src="images/mas-gradient.gif?raw=true" width="40%" height=auto />
</p>

In order to code these complex behaviour we used a graph representation illustrating the changing between states endowed by the agent. For the task delegation problem, the graph was the following:

<p align="center">
<img src="images/mas-graph.png?raw=true" width="40%" height=auto />
</p>

### 4. Results

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
