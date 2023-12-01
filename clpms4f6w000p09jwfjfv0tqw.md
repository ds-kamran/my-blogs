---
title: "Day 23/90 : 1) Jenkins Freestyle Project for DevOps Engineers."
datePublished: Fri Dec 01 2023 15:28:15 GMT+0000 (Coordinated Universal Time)
cuid: clpms4f6w000p09jwfjfv0tqw
slug: day-2390-1-jenkins-freestyle-project-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701444472043/4199024a-ec38-43f6-b324-072b5dcfda35.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701444484659/383e2610-2dc6-4a82-bfdb-f33161541065.png
tags: jenkins, cicd-cjy1vtdk2005kjjs17n8couc3

---

* create an agent for your app. ( which you deployed from docker in earlier task)
    
* Create a new Jenkins freestyle project for your app.
    

* In the "Build" section of the project, add a build step to run the "docker build" command to build the image for the container.
    

* Add a second step to run the "docker run" command to start a container using the image created in step 3.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444134803/de54b8d5-cdbf-48d4-9d35-b8641b1c6083.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444177404/67a99742-67b8-4666-918c-97fbd8b52b9f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444215431/dc4cbcfb-639f-4f46-9f5c-b7de6d115c07.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444230358/83b661b4-98aa-4642-a4b5-8f27d495ce58.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444262593/9b7ce6e2-ce85-464a-a6dc-ab98915330cf.png align="center")

Build Finished Successfully

Container list:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444326095/a545b10b-629f-49ba-ab4d-6a83087cf8ac.png align="center")

Image list:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444344963/e87495a5-f11b-46e0-a893-874ce9b74c9e.png align="center")

Clean-up

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701444415288/5f4e3ccb-2c1e-40f5-80a1-5f9f7bf29a89.png align="center")