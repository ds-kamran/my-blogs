---
title: "Day 10/90 Task: Advance Git & GitHub for DevOps Engineers"
datePublished: Tue Nov 14 2023 00:42:41 GMT+0000 (Coordinated Universal Time)
cuid: cloxm03b2000008lcey3m4mzt
slug: day-1090-task-advance-git-github-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699922493482/e2355c69-3de5-4339-ac86-5c5fe40a1706.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1699922520037/26dff232-018d-4c79-83bc-4883822c0dd7.webp
tags: github, gitcommands, 90daysofdevops, 90daysofdevops-chanllenge

---

Digging deep into git and GitHub terminologies with examples:

**Git Branching:** Git branching is a powerful feature that allows developers to work on different aspects of a project simultaneously, isolate changes, and manage collaborative development effectively.

**Git Revert and Reset: "git revert"** and **"git reset"** are both Git commands used to manage changes in a repository, but they serve different purposes.

Task 1:

**ubuntu@DevOps**:**~/Devops**$ cd Git/

**ubuntu@DevOps**:**~/Devops/Git**$ vi versio01.txt

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git status

On branch master

Untracked files:

  (use "git add &lt;file&gt;..." to include in what will be committed)

versio01.txt

nothing added to commit but untracked files present (use "git add" to track)

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout -b dev

Switched to a new branch 'dev'

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git commit -m "Added new Feature"

On branch dev

Untracked files:

  (use "git add &lt;file&gt;..." to include in what will be committed)

versio01.txt

nothing added to commit but untracked files present (use "git add" to track)

**ubuntu@DevOps**:**~/Devops/Git**$ git add .

**ubuntu@DevOps**:**~/Devops/Git**$ git commit -m "Added new Feature"

\[dev 4ee156e\] Added new Feature

 1 file changed, 1 insertion(+)

 create mode 100644 Git/versio01.txt

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git config --list

[user.name](http://user.name)\=ds-kamran

[user.email=ds.kamranarif@gmail.com](mailto:user.email=ds.kamranarif@gmail.com)

core.repositoryformatversion=0

core.filemode=true

core.bare=false

core.logallrefupdates=true

remote.origin.url=[https://ghp\_0F2dWhFt2SHqrRNToRwahsesfCUVqa3wbSF3@github.com/ds-kamran/Devops.git](https://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@github.com/ds-kamran/Devops.git)

remote.origin.fetch=+refs/heads/\*:refs/remotes/origin/\*

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout -b master

fatal: A branch named 'master' already exists.

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git push origin master

Everything up-to-date

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git push origin dev

Enumerating objects: 6, done.

Counting objects: 100% (6/6), done.

Compressing objects: 100% (2/2), done.

Writing objects: 100% (4/4), 359 bytes | 359.00 KiB/s, done.

Total 4 (delta 0), reused 0 (delta 0), pack-reused 0

remote: 

remote: Create a pull request for 'dev' on GitHub by visiting:

remote:      [https://github.com/ds-kamran/Devops/pull/new/dev](https://github.com/ds-kamran/Devops/pull/new/dev)

remote: 

To [https://github.com/ds-kamran/Devops.git](https://github.com/ds-kamran/Devops.git)

 \* \[new branch\]      dev -&gt; dev

**ubuntu@DevOps**:**~/Devops/Git**$ 

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699919766891/068e78c3-a9bd-40b2-bbb6-07dbed96a22b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699919789858/6cd3ce69-9bcc-4582-87ad-c046fb96b82a.png align="center")

**ubuntu@DevOps**:**~/Devops/Git**$ git revert 18f6481

**ubuntu@DevOps**:**~/Devops/Git**$ git commit -m "Reverted to the feature2 change "

\[dev cf77f6e\] Reverted to the feature2 change

 1 file changed, 4 insertions(+)

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ cat versio01.txt 

&lt;&lt;&lt;&lt;&lt;&lt;&lt; HEAD

This is the bug fix in development branch

This is a gadbad code

This feature will be gadbad everything from now

\=======

This is first feature of our application

\&gt;&gt;&gt;&gt;&gt;&gt;&gt; parent of 18f6481 (Added feature2 in development branch)

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git log --oneline

cf77f6e (**HEAD -&gt; dev**) Reverted to the feature2 change

ed3d381 Added feature4 in development branch

1588013 Added feature3 in development branch

18f6481 Added feature2 in development branch

4ee156e (**origin/dev**) Added new Feature

f0b2ad7 (**origin/master**, **master**) Adding branch, file and content

Task 2:

* Demonstrate the concept of branches with 2 or more branches with screenshot.
    

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout -b master

fatal: A branch named 'master' already exists.

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout  master

Switched to branch 'master'

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout -b UAT

Switched to a new branch 'UAT'

**ubuntu@DevOps**:**~/Devops/Git**$ vi first.txt

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git add .

**ubuntu@DevOps**:**~/Devops/Git**$ git commit -m "First file added in branch UAT"

\[UAT 763ef1b\] First file added in branch UAT

 1 file changed, 1 insertion(+)

 create mode 100644 Git/first.txt

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git push origin UAT

Enumerating objects: 6, done.

Counting objects: 100% (6/6), done.

Compressing objects: 100% (2/2), done.

Writing objects: 100% (4/4), 346 bytes | 346.00 KiB/s, done.

Total 4 (delta 0), reused 0 (delta 0), pack-reused 0

remote: 

remote: Create a pull request for 'UAT' on GitHub by visiting:

remote:      [https://github.com/ds-kamran/Devops/pull/new/UAT](https://github.com/ds-kamran/Devops/pull/new/UAT)

remote: 

To [https://github.com/ds-kamran/Devops.git](https://github.com/ds-kamran/Devops.git)

 \* \[new branch\]      UAT -&gt; UAT

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout master

Switched to branch 'master'

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout -b test

Switched to a new branch 'test'

**ubuntu@DevOps**:**~/Devops/Git**$ vi second.txt

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git add .

**ubuntu@DevOps**:**~/Devops/Git**$ git commit -m "Seconf file added in test"

\[test 934bb11\] Seconf file added in test

 1 file changed, 1 insertion(+)

 create mode 100644 Git/second.txt

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git push origin test

Enumerating objects: 6, done.

Counting objects: 100% (6/6), done.

Compressing objects: 100% (2/2), done.

Writing objects: 100% (4/4), 350 bytes | 350.00 KiB/s, done.

Total 4 (delta 0), reused 0 (delta 0), pack-reused 0

remote: 

remote: Create a pull request for 'test' on GitHub by visiting:

remote:      [https://github.com/ds-kamran/Devops/pull/new/test](https://github.com/ds-kamran/Devops/pull/new/test)

remote: 

To [https://github.com/ds-kamran/Devops.git](https://github.com/ds-kamran/Devops.git)

 \* \[new branch\]      test -&gt; test

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699921302000/a32ec1d5-c27d-4547-928b-cceb4736f6e4.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699921330756/31d9954b-3ed5-4a25-a9bd-802e76365cb1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699921358881/a5c111e1-2dc7-4cb2-b3d5-c7157a2e3abe.png align="center")

### **Add some changes to** `dev` **branch and merge that branch in** `master`

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout dev

Switched to branch 'dev'

**ubuntu@DevOps**:**~/Devops/Git**$ touch file1.txt

**ubuntu@DevOps**:**~/Devops/Git**$ git add .

**ubuntu@DevOps**:**~/Devops/Git**$ git commit -m "New file added in dev"

\[dev 4b5ada0\] New file added in dev

 1 file changed, 0 insertions(+), 0 deletions(-)

 create mode 100644 Git/file1.txt

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ 

**ubuntu@DevOps**:**~/Devops/Git**$ git checkout master

Switched to branch 'master'

**ubuntu@DevOps**:**~/Devops/Git**$ git merge dev

Updating f0b2ad7..4b5ada0

Fast-forward

 Git/file1.txt    | 0

 Git/versio01.txt | 7 +++++++

 2 files changed, 7 insertions(+)

 create mode 100644 Git/file1.txt

 create mode 100644 Git/versio01.txt

Checking in github

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699921926595/2e621a50-db1e-45dd-8a3d-a9a23a06ad6a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699921988603/ccf05306-1e14-43e4-8fcd-9831243b74bf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699922014521/66e9e950-298e-495d-a56b-41d490491bc6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699922051324/369e1cdf-6e3a-42ef-92e4-e2ce9c564bfd.png align="center")

Insigts

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699922198128/c8183c34-97cf-4660-8ce4-48b37d5ccf6d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699922264277/af8d4150-b928-4e3c-a6bf-cc23ad7021e1.png align="center")