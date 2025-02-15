# cloudmon
An agent based monitoring system, to check for configuration drift on aws instances

## Description

The purpose of this system is to exchage information about linux configuration on instances and docker
container configuration, and docker system configuration with each other and keep them validated against
a global config. This is to try and mitigate configuration drift.

Use golang to make a system that has a deploy node and pushes goroutine agents to ec2 instances.
The agents communicate with each other and assume roles of "Collectors" and "Emitters".

`Collectors`: Collect information and logs from other nodes and verify them against the global config.

`Emitters`: Read and transmit required info about themselves to the Collectors.

The aim is to build a self managing system to combat configuration drift.
