---
title: "Day 18/90 Task: Docker for DevOps Engineers"
datePublished: Sun Nov 26 2023 23:09:00 GMT+0000 (Coordinated Universal Time)
cuid: clpg3doup000209jw45w70cs4
slug: day-1890-task-docker-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701040116795/d8a45f8a-719e-41da-91d4-1982bbf2a1f2.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701040137008/9e72b87d-c751-4784-a236-b2873856e485.png
tags: docker, devops

---

**Docker Compose** is a tool for defining and running multi-container Docker applications. It allows you to use a YAML file to configure your application’s services. Then, with a single command, you can create and start all the services from your configuration. Compose works in all environments; production, staging, development, testing, as well as CI workflows. [It also has commands for managing the whole lifecycle of your application: start, stop, and rebuild services, view the status of running services, stream the log output of running services, and run a one-off command on a service](https://docs.docker.com/compose/) [<sup>1</sup>](https://docs.docker.com/compose/).

YAML:

YAML stands for "YAML Ain't Markup Language." It's a human-readable data serialization language often used for configuration files and data exchange between systems. YAML is commonly used in configurations for software applications, infrastructure as code (like Kubernetes or Ansible), and other scenarios where data needs to be organized in a readable and easy-to-understand format.

YAML's structure is defined by indentation and relies on whitespace indentation to represent data hierarchy, making it quite intuitive for humans to read and write. It uses key-value pairs, lists, and nested structures to represent data.

Here's an example of YAML syntax:

key1: value1 key2:

* item1
    
* item2
    
* item3 key3: subkey1: subvalue1 subkey2: subvalue.
    
    YAML is often preferred for its simplicity, readability, and ability to represent complex data structures concisely, which makes it popular for configuration purposes in various applications and systems.
    

TASK -1

Learn how to use the docker-compose.yml file, to set up the environment, configure the services and links between different containers, and also to use environment variables in the docker-compose.yml file.

Sample yaml file:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701016661431/4c4ed03c-9a59-476e-983d-1d515a142261.png align="center")

For docker compose we need a docker network, one backend (could be any database) and frontend (could be any application)

$&gt;docker-compose up -d #to build the image locally and run the image

$&gt; docker-compose down #to stop the container and network.

TASK-2

* Pull a pre-existing Docker image from a public repository (e.g. Docker Hub) and run it on your local machine. Run the container as a non-root user (Hint- Use `usermod` command to give user permission to docker). Make sure you reboot instance after giving permission to user.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701038024276/81c07c3f-a534-47f4-a8aa-79df76a5a99d.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701037850910/285fd3c5-5cd0-4d00-9a32-c261a311f84c.png align="center")

a) Inspect the container's running processes and exposed ports using the docker inspect command.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701037993953/3c8c5f49-e3fb-487a-a715-439a9c0de44c.png align="center")

* Use the docker logs command to view the container's log output.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701038089491/1511f61e-e076-4973-a646-22daa6971f15.png align="center")
    
    * Use the docker stop and docker start commands to stop and start the container.
        
* docker stop &lt;container\_id&gt;
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701038406513/3c0625e4-6f11-4c40-a4a8-80277e4ec5fc.png align="center")
    
    docker start &lt;container\_id&gt;
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701038471162/7e6e772c-b12e-4fb6-9ec6-e1f6bcd74bc3.png align="center")
    

* Use the docker rm command to remove the container when you're done.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701039996069/9912e0c3-4968-4cc8-9833-ae7c36a78c62.png align="center")