---
title: "Day 03/90 : Basic Linux Command"
datePublished: Thu Nov 02 2023 02:47:01 GMT+0000 (Coordinated Universal Time)
cuid: clogl5rd8000008jt6coxfwyr
slug: day-0390-basic-linux-command
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698893157507/35854dd5-5df9-4f0b-b330-2ee96ed21810.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1698893182284/bf07c863-aae9-4d86-ac40-6354a32a0558.avif
tags: linux, linux-for-beginners, linux-basics, 90daysofdevops

---

Assignment task to complete the basic Linux command.

**1.  To view what's written in a file.**

ubuntu@ip-172-31-21-173:~$ cat file1

Hello World

Basic commands in Linux

**2.  To change the access permissions of files.**

ubuntu@ip-172-31-21-173:~$ ls -ltr

total 4

\-rw-rw-r-- 1 ubuntu ubuntu 36 Nov  2 02:10 file1

ubuntu@ip-172-31-21-173:~$ chmod 400 file1

ubuntu@ip-172-31-21-173:~$ ls -ltr

total 4

\-r-------- 1 ubuntu ubuntu 36 Nov  2 02:10 file1

ubuntu@ip-172-31-21-173:~$ chmod 777 file1

ubuntu@ip-172-31-21-173:~$ ls -ltr

total 4

\-rwxrwxrwx 1 ubuntu ubuntu 36 Nov  2 02:10 file1

ubuntu@ip-172-31-21-173:~$

**3. To check which commands you have run till now.**

 ubuntu@ip-172-31-21-173:~$ history

    1  cd /

    2  pwd

    3  ls -ltr

    4  whoami

    5  grep ubuntu /etc/passwd

    6  cd /root

    7  su cd /root

**4. To remove a directory/ Folder.**

 ubuntu@ip-172-31-21-173:~$ mkdir -p parent/child1/child2/child3

ubuntu@ip-172-31-21-173:~$

ubuntu@ip-172-31-21-173:~$

ubuntu@ip-172-31-21-173:~$ rm -rvf parent

removed directory 'parent/child1/child2/child3'

removed directory 'parent/child1/child2'

removed directory 'parent/child1'

removed directory 'parent'

ubuntu@ip-172-31-21-173:~$

**5.  To create a fruits.txt file and to view the content.**

buntu@ip-172-31-21-173:~$ touch fruits.txt

ubuntu@ip-172-31-21-173:~$ cat fruits.txt

ubuntu@ip-172-31-21-173:~$

**6.  Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.**

ubuntu@ip-172-31-21-173:~$ touch fruits.txt

ubuntu@ip-172-31-21-173:~$

ubuntu@ip-172-31-21-173:~$

ubuntu@ip-172-31-21-173:~$ vi fruits.txt

ubuntu@ip-172-31-21-173:~$

ubuntu@ip-172-31-21-173:~$

ubuntu@ip-172-31-21-173:~$ cat fruits.txt

Apple

Mango

Banana

Cherry

Kiwi

Orange

Guavava

ubuntu@ip-172-31-21-173:~$ more fruits.txt

Apple

Mango

Banana

Cherry

Kiwi

Orange

Guavava

ubuntu@ip-172-31-21-173:~$ less fruits.txt

**7.  Show only the top three fruits from the file.**

 ubuntu@ip-172-31-21-173:~$ head -3 fruits.txt

Apple

Mango

Banana

ubuntu@ip-172-31-21-173:~$

**8.  Show only the bottom three fruits from the file.**

 ubuntu@ip-172-31-21-173:~$ tail -3 fruits.txt

Kiwi

Orange

Guavava

**9.  To create another file Colors.txt and to view the content.**

 ubuntu@ip-172-31-21-173:~$ vi colors.txt

ubuntu@ip-172-31-21-173:~$ cat colors.txt

Red

Pink

White

Black

Blue

Orange

Purple

Grey

**10. Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.**

 Vi color.txt

Esc+i

 Insert the fruit name

Esc+:wq!

**11.  To find the difference between fruits.txt and Colors.txt file.**

ubuntu@ip-172-31-21-173:~$ diff fruits.txt colors.txt

1,5c1,5

&lt; Apple

&lt; Mango

&lt; Banana

&lt; Cherry

&lt; Kiwi

\---

\&gt; Red

\&gt; Pink

\&gt; White

\&gt; Black

\&gt; Blue

7c7,8

&lt; Guavava

\---

\&gt; Purple