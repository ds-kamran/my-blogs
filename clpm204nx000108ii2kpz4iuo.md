---
title: "Day 22/90: Getting Started with Jenkins"
datePublished: Fri Dec 01 2023 03:17:05 GMT+0000 (Coordinated Universal Time)
cuid: clpm204nx000108ii2kpz4iuo
slug: day-2290-getting-started-with-jenkins
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701400594906/0f83f9d7-10ca-4c7d-84ef-f530c3971cff.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701400608811/48d00f6b-13ee-4e48-9fd2-5a21d2888b36.png
tags: jenkins, ci-cd, jenkins-devops

---

JENKINS:

In the realm of Continuous Integration and Continuous Deployment (CI/CD), Jenkins stands tall as a robust automation server, streamlining the software development lifecycle. Its versatile capabilities empower DevOps teams to automate repetitive tasks, ensuring seamless integration, testing, and deployment.

Key Components of Jenkins Pipeline as Code: Jenkins employs a powerful concept called "Pipeline as Code," allowing developers to define their CI/CD pipelines in a structured format using Groovy DSL or YAML syntax. This approach provides flexibility, version control, and easy maintenance of pipelines.

Plugins Ecosystem: Jenkins boasts an extensive library of plugins, catering to diverse needs. These plugins expand Jenkins' functionalities, enabling integrations with various tools and technologies for enhanced automation.

Distributed Builds: Jenkins enables the distribution of build tasks across multiple agents or nodes, facilitating faster builds and scalability. It optimizes resource utilization by executing jobs on available nodes in the Jenkins cluster.

Automation in Jenkins Automated Testing: Jenkins automates the execution of test suites as part of the CI process. With plugins for popular testing frameworks (e.g., JUnit, Selenium), it ensures code quality by running tests against different environments.

Continuous Deployment: Through integrations with configuration management tools like Ansible, Puppet, or Docker, Jenkins automates the deployment process. It triggers deployment tasks upon successful completion of build and testing phases.

Scheduled Jobs and Trigger Mechanisms: Jenkins enables scheduling of jobs at specified times or based on triggering events such as code commits. This automation reduces manual intervention, ensuring timely execution of tasks.

Notification and Reporting: Jenkins sends notifications via email, Slack, or other communication channels to keep stakeholders informed about build statuses, test results, and deployment outcomes. Additionally, it generates reports for performance analysis and trend tracking.

Benefits of Jenkins Automation Accelerated Time-to-Market: By automating build, test, and deployment processes, Jenkins significantly reduces manual intervention, accelerating the software delivery lifecycle.

Consistency and Reliability: Automation ensures consistency in the execution of tasks, reducing human errors and enhancing the reliability of the CI/CD pipelines.

Scalability and Flexibility: Jenkins' distributed architecture allows for easy scalability, accommodating increased workloads and diverse project requirements. Its flexible nature supports various development environments and toolchains.

In conclusion, Jenkins plays a pivotal role in DevOps by automating crucial stages of the CI/CD pipeline. Its robust features, plugin ecosystem, and emphasis on automation empower teams to streamline workflows, improve code quality, and achieve efficient software delivery.

EXAMPLE :

**Create a freestyle pipeline to print "Hello World!!**

STEP 1: Download and install JENKINS in your OS.

STEP 2: Jenkins always opens in port 8080.

STEP 3: Login to the jenkins using the login id and password.

STEP 4: After you will see a page like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701400118709/77874ade-30ff-4251-893e-fd34fe6bf530.png align="center")

STEP 5: GO to new item

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701400162491/78a6ee0b-97a9-4fa0-ba11-5dc560c8ac46.png align="center")

STEP 6: write a description

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701400223697/007d8f90-6a0f-4192-9496-4a4e97c155bc.png align="center")

STEP 7: Write the hello world in the BUILD Section

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701400354565/e4952e9c-2757-4ff9-bde3-db1da5b51ed0.png align="center")

STEP 8: Click on "Build now" to build the instruction

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701400417212/4216bd58-fbd7-4462-8b1b-2e68a375f70f.png align="center")

STEP 9: Click on console output to generate the output.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701400476640/33588513-2e65-466d-a5d2-3f7bbf366339.png align="center")

STEP 10: The build completed successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701400506525/09fdf677-9d7d-4a66-a593-33d9eda968e1.png align="center")

Concluding the task, the jenkins build completed within 10 steps.