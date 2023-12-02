---
title: "Day 28/90: Jenkins Agents"
datePublished: Sat Dec 02 2023 04:04:03 GMT+0000 (Coordinated Universal Time)
cuid: clpnj4dfo000309jl0wxx17sf
slug: day-2890-jenkins-agents
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701489803204/f3053c61-77b2-4566-ad74-0ff5cd3d9891.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1701489838843/a078e512-7aaa-4d6e-83b7-93d5600e001e.png
tags: docker, devops, jenkins, 90daysofdevops

---

TASK 01

* Create an agent by setting up a node on Jenkins
    
* Create a new AWS EC2 Instance and connect it to master(Where Jenkins is installed)
    
* The connection of master and agent requires SSH and the public-private key pair exchange.
    
* Verify its status under "Nodes" section.
    

Solution : An agent "dev-server" is being created.

Name : could be any name given to the node

Description: could be the description of the node

Remote root direct: is a directory in slave server used by agent

Label: should be the label name used in pipeline script could be different from node name.

Launch method: defines the method to Jenkins login to the slave server to perform action

Host : is the public ip of the slave host.

Credentials : could be the credentials of the default user of the slave host.

Key : is generated using RSA or ed25519

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701488154570/a876e1fd-775b-4672-955a-671ba1d7460c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701488175501/5a5bf89d-36c4-4672-8af9-aab2397edded.png align="center")

How to generate keys.

Go to the master host.

Note :the private key should be in the master host and public in the agent host.

RSA key :

$ssh-keygen # generating a public private keypair

ED25519:

**ubuntu@ds-kamran**:**~/.ssh**$ ssh-keygen -t ed25519

Generating public/private ed25519 key pair.

Enter file in which to save the key (/home/ubuntu/.ssh/id\_ed25519): ed-key

Enter passphrase (empty for no passphrase):

Enter same passphrase again:

Your identification has been saved in ed-key

Your public key has been saved in [ed-key.pub](file:////Users/kamranarif/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_filelist.xml)

Check in :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489126160/d26d1583-9da5-4364-b567-1e6f8984fac3.png align="center")

connect to agent:

$&gt; ssh &lt;[user.name](file:////Users/kamranarif/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_filelist.xml)\&gt;@&lt;ip\_address&gt;

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489240746/bd992ab4-a0d1-42d8-9a9e-b6474ef38ff1.png align="center")

Connected to the agent

Verify the agent:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489336190/1a4ae248-9274-4c2c-8bb5-a8e6ba161307.png align="center")

TASK 02:

* Run your previous Jobs (which you built on Day 26, and Day 27) on the new agent
    
* Use labels for the agent, your master server should trigger builds for the agent server.
    

Stage file:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489510593/9e96944a-1747-4385-ae30-728140057683.png align="center")

Error in build 22 and how it was resolved.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489557663/606e74d7-4523-45b0-aabf-1d6b4b99c5b9.png align="center")

Solution :

```bash
    # start the appormor system
    sudo systemctl start apparmor 
    # parse and reload all apparmor profiles of installed snap applications 
    sudo apparmor_parser -r /var/lib/snapd/apparmor/profiles/*
```

```plaintext
systemctl enable --now apparmor.service    
systemctl enable --now snapd.apparmor.service
```

the groovy pipeline file with the label.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489422265/021b418b-2540-4295-b900-693c70f8c83f.png align="center")

Console output:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489670527/78fc0d65-8bfd-4b41-9876-f6631d8979a0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701489682141/a83f5a38-aea9-455a-8bd2-025ac215264c.png align="center")