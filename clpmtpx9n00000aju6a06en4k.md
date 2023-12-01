---
title: "Day 23/90 : 2) Jenkins Freestyle Project for DevOps Engineers."
datePublished: Fri Dec 01 2023 16:12:58 GMT+0000 (Coordinated Universal Time)
cuid: clpmtpx9n00000aju6a06en4k
slug: day-2390-2-jenkins-freestyle-project-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701447122889/1feed1fe-3a2e-470a-8d87-2d70fafcdad2.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701447173878/4bc44d62-4b24-45b1-b251-ca78272a3d25.png
tags: docker, devops, jenkins, 90daysofdevops

---

* Create Jenkins project to run "docker-compose up -d" command to start the multiple containers defined in the compose file (Hint- use day-19 Application & Database docker-compose file)
    
* Set up a cleanup step in the Jenkins project to run "docker-compose down" command to stop and remove the containers defined in the compose file.
    

The Project Configuration:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701446940788/6d077f6f-5460-44ea-ba14-4fd7522f99b8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701446952086/f05f51be-5d0a-45e2-8151-473c79b70473.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701446964444/08b79078-2eb8-41ba-ac07-33f38e0acc87.png align="center")

Console OUTPUT:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701446877816/b52b4c75-b8f7-4e3a-9303-719751e8d88a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701446899964/98efa62a-3425-4bab-87fd-27eb9edc3e97.png align="center")

Running containers:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701446825637/91b60bd5-a553-4576-b679-d1d8e4acc566.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701446996482/9bac5e1b-b0df-405f-9e64-0c1a7f0f4b4a.png align="center")