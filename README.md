# rainbow_app_sim_stack

This repository is collection of application and simulation stack for [Project RAINBOW](https://rainbow-h2020.eu)

## Components

### Communication / Persistence Components

Both Application and Simulation stack need following components:

- Redis Database
- Rabbit Message Broker

Which is available at [Virtual-Origami's rabbitmqtt stack](https://github.com/virtual-origami/rabbitmqtt)

### Application stack

Application stack consists of following stateless components

- Personnel Localization and Motion Tracking Service 
- Robot Motion Tracking Service
- Collision Prediction and Avoidance Service

How to run the stack

```bash
$ cd rainbow_app_sim_stack
$ docker-compose -f application_stack.yml up
```

### Simulation stack

Simulation stack consists of following stateful components:

- Robot Motion Generator Service
- Personnel Motion Generator Service

How to run the stack

```bash
$ cd rainbow_app_sim_stack
$ docker-compose -f simulation_stack.yml up
```

## Steps to Bring the Stack Up

```bash

$ git clone git@github.com:virtual-origami/rabbitmqtt.git

$ cd rabbitmqtt
$ docker-compose up

$ docker network create iotstack

# Step 1: Start Rabbit MQ and redis
$ cd rabbitmqtt
$ docker-compose up

# Step 2: Run Application stack
$ cd rainbow_app_sim_stack
$ docker-compose -f application_stack.yml up

# Step 3: Run Simulation stack
$ docker-compose -f simulation_stack.yml up
```

### Interaction between components
![image](https://user-images.githubusercontent.com/48629016/133968239-09832970-3ffe-4fff-869f-a35047ac3c7b.png)

## Maintainers
The repository is maintained by:

- [Karthik Shenoy Panambur](mailto:she@biba.uni-bremen.de)
- [Shantanoo Desai](mailto:des@biba.uni-bremen.de)

[__BIBA - Bremer Institut für Produktion und Logistik GmbH__](www.biba.uni-bremen.de)

## FUNDING

* The development of this codebase and repository is driven through the [RAINBOW Project](https://rainbow-h2020.eu/). RAINBOW Project has received funding from the European Union’s Horizon 2020 programme under grant agreement number __871403__
* The development of this codebase and repository is driven through the [ASSURED Project](https://www.project-assured.eu/). ASSURED project is funded by the European Union's Horizon 2020 programme under Grant Agreement number __952697__

