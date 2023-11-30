---
title: "Day 20/90: Docker Cheat Sheet"
datePublished: Thu Nov 30 2023 03:45:32 GMT+0000 (Coordinated Universal Time)
cuid: clpknkv68000709ld7j876vel
slug: day-2090-docker-cheat-sheet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701315899220/0d61139e-0066-4dd3-bbc2-36d5cfca5701.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701315928849/b300eb46-6620-47d3-9508-3fcf5dcbc4b6.webp
tags: docker

---

list of docker commands for begineers

| COMMAND | EXPLANATION |
| --- | --- |
| docker build -t &lt;image\_name&gt; &lt;location of Dockerfile&gt; | to build an image |
| docker run -d --name=&lt;name of container&gt; &lt;image:latets&gt; | to run an image |
| docker ps | list of running container |
| docker ps -a | list of all container |
| docker stop &lt;container id&gt; | to stop a running container |
| docker start &lt;container id&gt; | to start a running container |
| docker rm &lt;container id&gt; | to remove a stopped container |
| docker image ls | list of images |
| docker image ls -a | list of all images |
| docker rmi -f &lt;image\_id&gt; | remove an image from local disk |
| docker image prune | to remove the non useful image from local disk |
| docker volume ls | list of all the  volumes |
| docker network ls | list of all the  network |
| docker-compose up | to build and run and image by compose file |
| docker-compose down | to  stop the image by compose file |