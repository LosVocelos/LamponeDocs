Project Contributions Overview
==============================

This document outlines the key contributions made to the ROS2 project, focusing on the development of the web-based visualization tool and the underlying communication infrastructure for our robot network.
This project serves as an administration page for controlling a network of robots operating within a simulated "city" environment, similar to a Ducky Town setup.

.. contents::
   :depth: 2
   :local:

The core objective of this project was to make a robust and intuitive system for monitoring and controlling a fleet of autonomous robots.
My involvement primarily focused on laying the foundational elements for visualization and inter-robot/server communication.

Project Planning and Task Distribution
--------------------------------------

A critical initial step was to develop a comprehensive project plan.
My responsibility encompassed the development of the visualization software.
However, a crucial part of this planning involved identifying and defining specific tasks that would be assigned to the camp participants.
This division ensured a clear roadmap for overall project development while providing valuable learning opportunities for the teams.
Key decisions regarding participant tasks included:

- Mapping the Roads: Defining methodologies and tools for participants to create accurate maps of the city roads.

- Robot Control Modules: Assigning the development of modules for controlling individual robot behaviors and navigation.

- Traffic Sign Identification: Tasking participants with implementing algorithms and systems for recognizing and interpreting traffic signs within the environment.

- Other Core Robot Functionalities: Delineating additional responsibilities related to autonomous navigation and obstacle avoidance.

Visualization Software Selection
--------------------------------

Following the project plan, research into existing ROS2 visualization tools was needed.
The goal was to identify a solution that offered flexibility, web-based accessibility, and ease of extension for custom data types.
After evaluating several options, rosboard was selected as the optimal choice due to its lightweight nature, real-time capabilities,
and straightforward architecture for integrating custom viewers,
although it doesn't provide an easy way for publishing messages from web out of the box.

Custom Messages and Services
----------------------------

To facilitate seamless and efficient communication within the robot network and between robots and the central server, a suite of custom ROS2 messages and services was designed.
These custom interfaces were made to represent the unique data structures and operational commands required for our "city" environment, ensuring:

- Robot State Reporting: Messages for transmitting robot turn signals, velocity, status (e.g., battery level, current task), and sensor data.

- Command and Control: Services and messages for issuing commands to traffic lights (e.g., navigate to point, stop, emergency brake).

- Environmental Data Exchange: Interfaces for sharing information about the simulated city environment, such as traffic light states, map of the roads or locations of other robots.

Visualization for Messages and Services
---------------------------------------

A significant part of the project involved integrating the custom messages and services with rosboard to create a meaningful and intuitive visualization.
This included:

- Developing custom rosboard viewers capable of parsing and rendering our unique message types.

- Designing visual representations that effectively convey robot states, movement paths, and sensor readings.

- Ensuring that the visualization provided real-time feedback, allowing operators to monitor the robot network's health and performance at a glance.

These contributions form the backbone of the project's administration and visualization capabilities, providing a solid foundation for further development and enabling effective control and monitoring of the robot fleet.