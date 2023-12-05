---
title: "Day 31/90 : Launching your First Kubernetes Cluster with Nginx running"
datePublished: Tue Dec 05 2023 02:22:02 GMT+0000 (Coordinated Universal Time)
cuid: clprpsqx8000c08lgdaau2obw
slug: day-3190-launching-your-first-kubernetes-cluster-with-nginx-running
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701743014533/2356bd01-c59a-4865-9717-b6aa406d5769.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701742912549/ea3de62e-fd53-481a-aed2-9393ad057da4.jpeg
tags: kubernetes, devops, minikube, kubeweekchallenge

---

**MiniCube:** Minikube is a lightweight Kubernetes implementation that creates a VM on your local machine and deploys a simple cluster containing only one node. Minikube is available for Linux, macOS, and Windows systems.

The Minikube CLI provides basic bootstrapping operations for working with your cluster, including start, stop, status, and delete.

Start a pod in nginx:

1) start a minikube:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701739611315/e5220c07-2d41-4cf8-a1d7-5965c805db72.png align="center")

**POD:** A Kubernetes [*Pod*](https://kubernetes.io/docs/concepts/workloads/pods/) is a group of one or more Containers, tied together for the purposes of administration and networking. The Pod in this tutorial has only one Container. A Kubernetes [*Deployment*](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) checks on the health of your Pod and restarts the Pod's Container if it terminates. Deployments are the recommended way to manage the creation and scaling of Pods.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701739787920/641570aa-80c5-421c-bebd-7ad50aefb200.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701739832432/088537f6-b610-4d51-be1a-bff7bafd1372.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701739896284/d684b066-a039-4d2b-b085-2af627ae3449.png align="center")

By default, the Pod is only accessible by its internal IP address within the Kubernetes cluster. To make the `hello-node` Container accessible from outside the Kubernetes virtual network, you have to expose the Pod as a Kubernetes [*Service*](https://kubernetes.io/docs/concepts/services-networking/service/).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701740057957/1048ce50-3855-4173-b122-d4e0835d6c8f.png align="center")

Clean Up:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701740406214/3e3405c0-783c-4e3e-b3dd-95529f884ac2.png align="center")