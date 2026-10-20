## What is ECS? 
1. It is a managed container orchestrator for AWS.
2. It is managed by AWS exclusively.
3. Main Purpose: Manage the lifecycle of a container (eg: create/restart/destroy).
4. They are also responsible for deploying and load balancing the application across multiple servers.
5. Auto-scale to handle variance in traffic.
6. Rolling out changes to the code efficiently without disrupting the end user's experience.
7. **ECS:**
   1. The brains behind how your containers are deployed.
   2. It works only with containers.
   3. It needs the underlying infrastructure, like servers, to run and maintain those containers.
   4. ECS cluster: It is a bunch of resources that the containers will run on. Basically, it is the physical infrastructure.
      1. So it is going to be based on a bunch of EC2 virtual machines.
   5. With the EC2 launch type, the underlying EC2 instances need to be managed.
   6. The ECS control plane is used for this.
   7. Managing EC2:
      1. Install Docker.
      2. Install the ECS agent -> The EC2 servers should have a special agent so that the ECS control plane can talk to them and give them instructions.
      3. Install a firewall so that access is given only to certain ports and not opened up to any unnecessary vulnerabilities.
      4. Apply routine patches and upgrades so that the servers are all up to date.
      5. All of these need to be done by the user. This way, full control of the infrastructure is under the user's control.

## ECS Fargate
1. It follows a serverless architecture.
2. When an application is created and sent to ECS, it will talk to Fargate to create servers on demand to deploy the application.
3. Then ECS deploys the containers onto the created infrastructure.
4. Only pay for what you use.

## ECS task definition
1. It is a file that acts as the blueprint that describes how a container should launch.
2. It will contain all the container-specific configurations, like the CPU, memory, what image it should use, what specific ports should be open, what volumes should be attached to it.
3. A task definition file contains all of the configuration for more than one container.
4. An entire application file can be put in one task definition file or can be split out depending on the configuration.
5. Task:
   1. A task is an instance of a task definition.
   2. A task definition is just instructions.
   3. A task is created when we want to create an instance of our application.

## ECS Services and load balancers
1. A service ensures that a certain number of tasks are running at all times.
2. Restarts containers that have exited/crashed.
3. If an EC2 instance fails while working on a task, the service will restart the task on a working EC2 instance.
4. A load balancer can be assigned to the user's service to route external traffic.
5. It also automatically detects the addition and deletion of instances.
