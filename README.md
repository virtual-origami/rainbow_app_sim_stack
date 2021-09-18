# rainbow_app_sim_stack

This repository is collection of application and simulation stack for project Rainbow



### Dependencies

Both Application and Simulation stack need following components

- Redis database
- Rabbit message queue broker

Thanks to **Shan** **desai** the stack is available at git@github.com:virtual-origami/rabbITMQ.git

```bash
# clone the repository
$ git clone git@github.com:virtual-origami/rabbITMQ.git
```

```bash
# run the stack
$ docker-compose -f prototype/docker-compose.prototype.yml up
```



### Application stack

Application stack consists of following stateless components

- Personnel Localization and Motion Tracking Service 
- Robot Motion Tracking Service
- Collision Prediction and Avoidance Service



How to run the stack

```bash
$ cd rainbow_app_sim_stack/application_stack
$ docker-compose up 
```



### Simulation stack

Simulation stack consists of following stateful components 

- Robot Motion Generator Service
- Personnel Motion Generator Service
- Visualization Service



How to run the stack

```bash
$ cd rainbow_app_sim_stack/simulation_stack
$ docker-compose up 
```



### Putting it altogether

```bash
# Step 1: Create network with name iotstack 
$ docker network create iotstack

# Step 1: Start Rabbit MQ and redis
$ cd rabbITMQ
$ docker-compose -f prototype/docker-compose.prototype.yml up

# Step 2: Run Application stack
$ cd rainbow_app_sim_stack/application_stack
$ docker-compose up 

# Step 3: Run Simulation stack
$ cd rainbow_app_sim_stack/simulation_stack
$ docker-compose up 
```
