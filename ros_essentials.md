# ROS Essentials

There are two fundamental concepts in ROS, which are: **Nodes** and **Topics**. 

## Nodes:
These are software processes that do 'stuff' (e.g. process data, command hardware, execute algorithms). Nodes provide modularity to robotic projects that use ROS. They are often written in C++ or Python. In this course, we will use Python to write them. ROS is only compatible with Python 2.7.x.

## Topics:
Transport information between nodes, in the form of messages.

> In a real robot application you will often have to deal with a large number of nodes and topics. It is important to know which nodes are talking to each other, and what topics are being used to pass the information (messages) between nodes.

#### Remainder: Don't forget to source your workspace if you want to use ROS commands!
``` $ source $HOME/hrwros_ws/devel/setup.bash ```

## ROS Node summary:

There are three main ways to inspect a ROS node:

* Simply list all currently running nodes in the terminal:
`rosnode list`
* Make a visual graph of all running nodes and their connections:
`rqt_graph`
* List information about a specific node in the terminal:
`rosnode info <node_name>`

#### Question 1
> In robotics, we often have to interact with the real-world. One type of device we can use to interact with the environment is a sensor: we can sense a desired quantity from the environment and turn it into data.

Are sensors an example of a ROS node, or ROS topic?

- [x] Node
- [ ] Topic

*Answer* : **Node**, because a sensor processes information and then provides data. It does not transport it between nodes.

## ROS Topic summary:

*ROS topics* transport information between nodes. This information is organized as a data structure and can have different data types. Topics can be identified by their name and their type. You can think of topics as strongly typed message buses. Any node can connect to it to send or receive data, as long as they are the right type.

As with nodes, there are three ways to inspect topics:

* Display a list of all topics that are currently being exchanged between active nodes
`rostopic list`
* Display information about the data structure of a specific topic
`rostopic info <topic_name>`
* Print the current content of a topic in the terminal
`rostopic echo <topic_name>`

**Important detail:** Do not forget the "/" before node and topic names!

