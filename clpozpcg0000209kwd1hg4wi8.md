---
title: "Day 30/90: Kubernetes Architecture"
datePublished: Sun Dec 03 2023 04:36:01 GMT+0000 (Coordinated Universal Time)
cuid: clpozpcg0000209kwd1hg4wi8
slug: day-3090-kubernetes-architecture
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701578135077/d13a7202-f11a-4956-abad-53649d9ae828.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701578157329/759e2442-50a0-4e10-8c3a-c855cacba056.png
tags: docker, kubernetes, devops, kubeweekchallenge

---

What is Kubernetes? Write in your own words and why do we call it k8s?

Kubernetes is an open-source platform designed to automate deploying, scaling, and managing containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF).

At its core, Kubernetes allows you to abstract the underlying infrastructure, enabling you to deploy applications without worrying about the specific hardware or environment where they run. It works with containerization technologies like Docker, enabling developers to package their applications and dependencies into containers for easy deployment and management.

The alphabets between K and S are 8, so in short it is also called K8S.

**What are the benefits of using k8s?**

1. Kubernetes provides functionalities for:
    
    1. **Container Orchestration:** It manages the deployment, scaling, and operation of application containers across clusters of hosts.
        
    2. **Service Discovery and Load Balancing:** It automatically assigns network addresses to containers and balances the load to ensure the applications are highly available.
        
    3. **Self-healing Capabilities:** If a container or node fails, Kubernetes can automatically restart or reschedule containers to maintain the desired state.
        
    4. **Scaling:** It allows automatic scaling of applications by adding or removing container instances based on resource usage.
        
    5. **Rolling Updates and Rollbacks:** Kubernetes facilitates updating applications without downtime by gradually updating instances, and it allows reverting to previous versions if needed.
        
    
    **Explain the architecture of Kubernetes:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701577153552/f7ae1a58-c213-4dc9-bc33-4e47e02b4598.png align="center")
    

K8S cluster requires minimum 2 node which make it a master-worker architecture.

Master has services like :

Scheduler: Which schedules the job, health checkup of nodes.

etcd: is kind of a database inside the master node, it stores all the information and mata data of K8S.

Controller Manager: has all the information of Master and worker node, every action and failure information.

API Server : is the only service which interacts with worker node, kubectl, and Master node.

Kubectl : it is a cli tool which is used to interact with the master node.

CNI Network : is the Container network interphase, which makes the connection between master-worker node.

user: are the end user which gives the instruction

Worker Node:

Service Provide : has all the information of outside of the worker node and shares information inside the worker node also let the end user access the application.

Kubelet: is the service which stays in the worker node but share all the update of worker node to the master node by communicating it with API server.

**What is Control Plane?**

In Kubernetes, the Control Plane, also known as the Master Node, is the core component responsible for managing the cluster and its state. It's the brain behind orchestration and decision-making within the Kubernetes architecture.

The Control Plane consists of several key components:

1. **API Server:** This component serves as the entry point for all administrative tasks and management of the cluster. It validates and processes REST operations, allowing users and other components to interact with the Kubernetes cluster.
    
2. **Scheduler:** The Scheduler is responsible for assigning newly created pods (the smallest deployable units in Kubernetes) to nodes based on resource availability, constraints, and other policies.
    
3. **Controller Manager:** This component runs controller processes that regulate the state of the cluster. Controllers watch the state of the cluster via the API server and take action to move the current state towards the desired state.
    
4. **etcd:** This is a distributed key-value store that stores the cluster's configuration data, state, and metadata. It's critical for the functioning of the Control Plane as it holds the authoritative data about the cluster.
    

These components work together to maintain the desired state of the cluster, manage resources, and ensure that applications are running as specified in the deployment configurations. The Control Plane interacts with worker nodes, where the actual application workloads are run, instructing them on what and how to run based on the configurations provided.

Having a separate Control Plane and worker nodes architecture ensures better scalability, high availability, and fault tolerance in Kubernetes clusters.

**Write the difference between kubectl and kubelets.**

* **kubectl**:
    
    * `kubectl` is a command-line interface (CLI) used to interact with the Kubernetes cluster's API server.
        
    * It allows users to perform various actions on the cluster, such as deploying applications, managing resources (pods, services, deployments), checking cluster status, scaling applications, and more.
        
    * This tool is typically used by administrators, developers, or operators to control and manage the Kubernetes cluster from the command line.
        
    * `kubectl` commands are issued from an external machine or user's local environment to manage the Kubernetes cluster.
        
* **kubelet**:
    
    * `kubelet` is an agent that runs on each individual node within a Kubernetes cluster.
        
    * It's responsible for communicating with the Control Plane (the master node) and managing the containers running on its node.
        
    * The kubelet receives Pod specifications (manifests) via the Kubernetes API server and ensures that the containers described in these specifications are running and healthy on the node.
        
    * It handles tasks like starting and stopping containers, reporting node status, monitoring containers, and more. Essentially, it's responsible for maintaining the node's runtime environment and the Pods' lifecycle.
        

In summary, `kubectl` is a CLI tool used for cluster management and administration from an external machine, while `kubelet` is an agent running on each node within the cluster, responsible for managing containers and their lifecycle on that specific node.

**Explain the role of the API server:**

The API server in Kubernetes is a core component and the central management entity of the entire Kubernetes control plane. It serves as the front-end to the Kubernetes cluster and is responsible for numerous crucial functions:

1. **Endpoint for Cluster Operations:** The API server acts as the front-end to the Kubernetes control plane. It exposes the Kubernetes API, which allows users, `kubectl`, and other components to interact with the cluster, perform operations, and manage resources.
    
2. **Validation and Admission Control:** It validates and processes API requests, ensuring they adhere to security policies, access controls, and other constraints defined for the cluster. Admission control mechanisms allow administrators to enforce custom rules or policies for resource creation and modification.
    
3. **State Storage:** The API server serves as a gateway to the cluster's etcd datastore. It stores the cluster's configuration details, including information about objects such as pods, services, deployments, replica sets, and more. All cluster state information is stored in etcd.
    
4. **Synchronization and Communication:** The API server communicates with various components within the control plane, such as the Scheduler, Controller Manager, and kubelet, to manage the cluster's state. It ensures that desired state configurations are met and synchronizes information across the cluster.
    
5. **Authentication and Authorization:** It handles authentication of users and components interacting with the cluster. It verifies user identities and authorizes their actions based on RBAC (Role-Based Access Control) policies, ensuring secure access to the cluster's resources.
    
6. **Watch and Notify Mechanism:** It supports the watch mechanism, allowing clients to set up watches for specific resources. This enables real-time notifications about changes to these resources, allowing for reactive actions based on the observed state changes.
    

In summary, the API server is the primary interface through which users, administrators, and various components interact with the Kubernetes cluster. It validates requests, stores the cluster state, manages communication within the control plane, and enforces security policies to maintain the cluster's stability, security, and consistency.