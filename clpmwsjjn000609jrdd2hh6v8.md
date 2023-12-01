---
title: "Day 24/90: Complete Jenkins CI/CD Project"
datePublished: Fri Dec 01 2023 17:38:59 GMT+0000 (Coordinated Universal Time)
cuid: clpmwsjjn000609jrdd2hh6v8
slug: day-2490-complete-jenkins-cicd-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701452310072/b5bf0412-0ce5-4b37-a59a-c3b2a16a87bd.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701452335416/3661d4b8-06c4-431f-80e1-99e033f71da7.png
tags: jenkins, jenkins-devops, jenkins-pipeline

---

1) Forked the Repo : node-todo-cicd

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701448000938/388caae8-ef27-493f-be79-6bdb4548b54f.png align="center")

2) Create a connection to your Jenkins job and your GitHub Repository via GitHub Integration.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701448206937/9fa75977-6b43-4003-b8a6-ba58a996adfa.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701451099342/7ee2975d-2b58-4ecf-8f72-e2bb8e22b9a3.png align="center")

3) Webhook :

In Jenkins, a webhook is a mechanism used to trigger Jenkins jobs automatically in response to specific events that occur in external systems, such as code repository updates or external application events.

Webhooks in Jenkins are configured to listen for notifications from external services or systems. When a predefined event, such as a code push to a version control system like GitHub, GitLab, or Bitbucket, occurs, a webhook sends a HTTP POST request to a specific URL endpoint in Jenkins.

Once Jenkins receives this webhook payload, it triggers a job or a pipeline defined to respond to that event. This allows for immediate or scheduled execution of Jenkins jobs, initiating the defined workflows without manual intervention.

Configuring webhooks in Jenkins involves setting up the URL endpoint that the external system will notify upon the occurrence of the specified event. Within Jenkins, plugins or integrations are utilized to handle incoming webhook requests and trigger the associated jobs or pipelines based on the received payload.

By utilizing webhooks, Jenkins facilitates seamless automation, ensuring that the CI/CD pipelines are triggered automatically in response to relevant external events, thereby enhancing the efficiency of the software development lifecycle.

Task 2:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701452097932/07a7918d-21e9-4624-9e32-3f738b7e7416.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701452110851/c39c005c-d7d7-4a1f-a000-a208806dbf07.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701452127637/7323f529-c1aa-47fd-801e-ea27d6576fab.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701452174511/e053c5a8-652a-496e-81fe-fd40bfb914ff.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701452194771/63767c13-2a9a-4892-8f63-966f9c59ec9b.png align="center")