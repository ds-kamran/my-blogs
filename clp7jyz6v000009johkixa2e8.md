---
title: "Day 16/90: Docker for DevOps Engineers"
datePublished: Mon Nov 20 2023 23:43:32 GMT+0000 (Coordinated Universal Time)
cuid: clp7jyz6v000009johkixa2e8
slug: day-1690-docker-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700523638931/09decf5a-2c51-4f56-9851-70c8af87cdde.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1700523806917/e0ab54a4-64a8-47b8-8928-330dce3396d4.jpeg
tags: docker, devops

---

Docker is a platform and tool designed to help developers build, deploy, and run applications in containers. Containers are lightweight, portable, and self-sufficient units that package software and all its dependencies, allowing applications to run consistently across different environments.

With Docker, developers can create, distribute, and manage these containers easily. It provides a way to package an application and its dependencies into a standardized unit for software development. This technology allows for isolation of applications, efficient resource utilization, and simplification of deployment processes.

Docker uses a client-server architecture. The Docker Engine serves as the server, managing containers, images, networks, and storage. Developers interact with Docker through its command-line interface or graphical user interfaces, enabling them to build, share, and deploy applications seamlessly.

Commands:

docker pull nginx:latest #pull the latest nginx docker image from docker hub

docker run -d nginx #run the docker image

docker container ls #check the list of running files

docker inspect &lt;image\_id&gt; #provides the details of how the image is built

docker stats # displays the statistics of running containers.

docker top &lt;container\_id&gt;. #shares the list of running processes in the mentioned container id

docker save &lt;image\_id&gt; &gt; &lt;filename.tar&gt; #save a backup of the image in .tar format in pwd.

docker load -i nginx.tar #load the saved image file