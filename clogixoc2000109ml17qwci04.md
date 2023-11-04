---
title: "Day 02/90: Basic Linux Commands"
datePublished: Thu Nov 02 2023 01:44:45 GMT+0000 (Coordinated Universal Time)
cuid: clogixoc2000109ml17qwci04
slug: day-0290-basic-linux-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698889371059/69443bb4-1fc9-478d-ae86-c8654d86fd5b.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1698889459598/1144ba11-df9d-4c9e-82d1-266ab90cf474.webp
tags: unix, devops, devops-articles, 90daysofdevops, 90daysofdevopschallenge

---

**What is Linux:**

 Linux is an open-source, Unix-like operating system kernel that serves as the core component of many different Linux distributions, commonly referred to as "Linux" as well. It was created by Linus Torvalds in 1991 and has since become a widely used operating system kernel, particularly in the world of servers, embedded systems, and various computing devices.

 Linux is known for its stability, security, and flexibility. It is used in a wide range of applications, from servers and supercomputers to mobile phones, IoT devices, and even desktop computers. Popular Linux distributions (or distros) that build upon the Linux kernel include Ubuntu, Fedora, CentOS, Debian, and many more.

 Key features and characteristics of Linux include:

 **Open Source:** Linux is distributed under open-source licenses, which means that its source code is freely available for anyone to view, modify, and distribute. This open nature encourages collaboration and innovation.

 **Multiuser and Multitasking:** Linux is a multiuser and multitasking operating system, allowing multiple users to work on the system simultaneously and run multiple processes concurrently.

 **Command-Line Interface:** Linux provides a powerful command-line interface (CLI), which is favored by many administrators and developers for its efficiency and flexibility.

 **Package Management:** Most Linux distributions include package management systems that simplify software installation, updates, and removal. Common package managers include APT (used in Debian and Ubuntu) and YUM (used in CentOS and Fedora).

 **Security:** Linux is known for its strong security features, including user and group permissions, robust firewall options, and regular security updates.

 **Customization:** Users can customize their Linux distributions by choosing from a wide range of desktop environments, software packages, and system settings.

 **Device Support:** Linux supports a wide variety of hardware architectures, making it suitable for different devices and systems.

 **Free and Low-Cost:** Most Linux distributions are available for free, which is a significant advantage for organizations and individuals looking to reduce software licensing costs.

 **Server and Data Center Usage:** Linux is a popular choice for server and data center environments due to its reliability, performance, and low total cost of ownership.

 **Community and Support:** The Linux community is large and active, providing a wealth of resources, forums, and documentation for users seeking help and information.

 Overall, Linux has a strong presence in various sectors of the computing industry, and it continues to gain popularity as a desktop operating system, especially among developers and power users who appreciate its open nature and the ability to tailor it to their specific needs.

**Linux Architecture:**

Linux architecture refers to the underlying design and organization of the Linux operating system. Linux is based on a monolithic kernel architecture, and it provides a foundation for various components and layers that work together to manage hardware resources, execute applications, and provide a stable computing environment. Here's an overview of the key components and layers of the Linux architecture:

**Kernel:** The Linux kernel is the core component of the operating system. It interacts directly with the hardware, managing hardware resources such as the CPU, memory, storage, and peripherals. It is responsible for process management, memory management, device drivers, and system calls. The kernel is loaded into memory when the system boots and remains in memory as long as the system is running.

**System Libraries:** On top of the kernel, Linux provides a set of system libraries that serve as an interface between applications and the kernel. These libraries include the GNU C Library (glibc) and various other libraries that provide essential functions and system calls. They help developers write software that can interact with the kernel and hardware.

**System Utilities:** Linux includes a wide range of system utilities and command-line tools that perform various tasks, from managing files and processes to configuring network settings and system administration. Common utilities include the shell, file management tools, text editors, and network utilities.

**Shell:** The shell is the command-line interface that allows users to interact with the operating system. It interprets user commands and executes them, providing a powerful way to manage and control the system. Common Linux shells include Bash (Bourne-Again Shell), Zsh, and others.

**User Space:** Above the kernel and system libraries, the user space encompasses all the user applications and services running on the system. This includes graphical user interfaces, web servers, databases, and a wide range of software that users interact with.

**Desktop Environment (Optional**): In desktop Linux distributions, a graphical desktop environment is provided to enhance the user experience. Common desktop environments include GNOME, KDE, Xfce, and more. These environments provide a graphical user interface with windows, icons, and menus.

**Application Layer:** The application layer includes user-installed software, both open-source and proprietary, such as web browsers, office suites, multimedia players, and development tools. Users can choose and install the applications they need.

**Device Drivers:** Device drivers are software components that enable communication between the kernel and hardware devices. Linux includes a wide range of built-in drivers, and additional drivers can be added as needed to support specific hardware.

**File System:** Linux supports various file systems, including ext4, XFS, and Btrfs, for managing data storage. The file system provides a structured way to organize and store files and data.

**Network Stack:** Linux features a comprehensive network stack that enables network communication, including protocols for Ethernet, Wi-Fi, TCP/IP, and more. It allows Linux systems to function as network servers, routers, or clients.

Linux's modular and open architecture allows for customization, expansion, and adaptability to various computing needs. Users and developers can modify and extend the system by adding or changing components, which is one of the strengths of the Linux ecosystem. This architecture, combined with the open-source nature of Linux, has led to its widespread use in a wide range of computing environments.

**Flavours of Linux:**

Linux "flavors" or distributions (often referred to as Linux distros) are different versions of the Linux operating system that are built upon the Linux kernel. These distributions package the kernel with various software, libraries, desktop environments, and configuration tools to create a complete and usable operating system. Each Linux distribution is designed to meet specific use cases, user preferences, and requirements. Here are some of the most popular and widely used Linux distributions:

**Ubuntu:** Ubuntu is one of the most popular Linux distributions, known for its user-friendly approach. It comes in several flavors, including Ubuntu Desktop with the GNOME desktop environment, Ubuntu Server, Ubuntu Mate, and others.

**Debian:** Debian is known for its stability and strong commitment to free and open-source software. It serves as the basis for many other Linux distributions, including Ubuntu.

**Fedora:** Fedora is a community-driven distribution sponsored by Red Hat. It emphasizes cutting-edge software and technologies, making it a good choice for developers and early adopters.

**CentOS:** CentOS is based on the source code of Red Hat Enterprise Linux (RHEL). It is known for its long-term support and is often used for servers and enterprise environments.

**openSUSE:** openSUSE is another community-driven distribution known for its flexibility and strong support for the KDE desktop environment.

**Arch Linux:** Arch Linux is a rolling-release distribution that targets experienced users who want a highly customizable system. It has a do-it-yourself philosophy and offers the Arch User Repository (AUR) for software installation.

**Gentoo:** Gentoo is a source-based distribution, meaning that users compile most of the software from source code. It is highly customizable and targets advanced users.

**Mint:** Linux Mint is based on Ubuntu and focuses on providing a user-friendly and aesthetically pleasing desktop experience. It comes with the Cinnamon desktop environment by default.

**Kali Linux:** Kali Linux is designed for cybersecurity professionals and enthusiasts, offering a wide range of tools for penetration testing, ethical hacking, and digital forensics.

**Slackware:** Slackware is one of the oldest Linux distributions and is known for its simplicity and minimalism. It's often chosen by users who prefer manual system configuration.

**Zorin OS:** Zorin OS is designed to be user-friendly and appealing to those transitioning from other operating systems, such as Windows. It offers a Windows-like interface.

**Puppy Linux:** Puppy Linux is a lightweight distribution ideal for older hardware or as a portable system. It can run entirely in RAM, making it very fast.

**Elementary OS:** Elementary OS is known for its sleek and elegant design, making it a great choice for users who appreciate a visually appealing desktop.

These are just a few examples, and there are many more Linux distributions available, each with its unique features and target audiences. Users can choose a distribution based on factors such as their skill level, intended use (desktop, server, security, etc.), and personal preferences for software, desktop environments, and design aesthetics.

**Basic commands of Linux/Unix:**

| **Sr. No** | **Commands** | **Definition** |
| --- | --- | --- |
| 1 | mkdir | command used to make directory |
| 2 | ls | list the files in present directory |
| 3 | ll | list all files in the present directory |
| 4 | date | display the present date of the os |
| 5 | clear | clear the screen |
| 6 | ps | show the running process |
| 7 | top | top process running in the bg taking memory |
| 8 | nohup | run the job in the background |
| 9 | touch | to generate an empty file |
| 10 | cat | display the content of the files |
| 11 | nano or vim | vi editor is used to edit/open a new file. |
| 12 | cd | change directory |
| 13 | pwd | show present working directory |
| 14 | whoami | display the login user |
| 15 | grep | find a keyword from a file |
| 16 | find | find a file in the present directory |
| 17 | history | history of the inputs made by the user |
| 18 | rm | remove file from the directory |
| 19 | mv | move the file from one to another directory |
| 20 | cp | copy the file in the directory |
| 21 | chmod | change the file permission |
| 22 | wc | count the number of words in the file |
| 23 | sudo | becoming the super user |
| 24 | cal | display the calender |
| 25 | df | show the disk partitions and disk files |
| 26 | ifconfig | display the ipaddress of the machine |
| 27 | useradd | add a new user |
| 28 | passwd | change the password of the user |
| 29 | wget | to download the file from the internet |
| 30 | tar -xf | to unzip the file |
| 31 | info | high level information of all the commands |
| 32 | cat /proc/version | to find the version of the OS. |
| 33 | who | present user information |
| 34 | echo | display, print a statement in the screen |
| 35 | alias | create shortcut for a combination of commands |
| 36 | kill | this command is used to kill running process using pid |
| 37 | chown | change the owneship of the file |
| 38 | tail | show the bottom 10 lines of the file |
| 39 | head | show the top 10 lines of the file |
| 40 | more | it is used to display a file in page form |
| 41 | less | it used to display less info of a file |
| 42 | rmdir | remove an empty directory |
| 43 | du | display disk usage of files and directories |