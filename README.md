# OSS Guide
In today's world, one cannot imagine teams collaborating on projects without the use of Git and GitHub. Projects require a version control system for tracking commit history, collaborating with developers around the world which syncs together and remains a single source of truth.

The following guide is designed for beginners who want to understand working collaboratively using Git and GitHub. I assume that the reader has some prior knowledge in programming and is at least procificent in any one programming language. It is suggested to follow this guide as a hands-on example. Additionally it is recommened to execute the commands yourself and read the resources providing in suggested reading.

# Obejectives
While there's too much to cover and too less time, we will restrict this guide to the following:
- Understanding Git and GitHub, their use cases and differences
- Essential Git commands
  1. `git init`
  2. `git add` 
  3. `git commit`
  4. `git status`
  5. `git log`
  6. `git checkout`
  7. `git branch`
  8. `git push`
  9. `git pull`
  10. `git merge`
  11. `git clone`
- Contribution workflow - forking, pushing, raising PRs, merging PRs, etc

# About the Speaker
I'm [Mahendra Dani](https://mahendradani.vercel.app), CS undergrad and I live on the terminal.

Let's Connect: 
- [Website](https://mahendradani.vercel.app) 
- [GitHub](https://github.com/MahendraDani) 
- [Linkedin](https://linkedin.com/in/mahendra-dani)

## Why you should trust me?
I have been contributing to Open Source since 2022 both individually and via programs. I have contributed to [The Palisadoes Foundation](https://www.palisadoes.org/), [AsyncAPI](https://www.asyncapi.com/), [JSON Schema](https://json-schema.org/) and more.

- GSSoC'23 - [Merged 30 PRs](https://docs.google.com/document/d/1ycciFlr7JYz9tnIt1v2YYiLOkQLqvz6hsJQTcUoSrZE/edit?tab=t.0#heading=h.sre7fun677kz) in 4 projects during a period of 3 months securing the position of top 113th contibutor in the program.
- Hacktoberfest'23 - Secured my spot in Hall of Fame'23 by merging 4 PRs
- Pre GSOC'23 - Actively contributed to [Palisadoes Foundation](https://github.com/PalisadoesFoundation/talawa-admin/pulls?q=is%3Apr+is%3Aclosed+author%3AMahendraDani)
- Prev Web Team member at GDSC VIT Bhopal and Open Source Club.

Read more about my journey in tech on my [blog](https://mahendradani.vercel.app/blogs/hello-world) 

# Prerequisites
Before starting with the guide, please make sure to :
- Create your Github Account.
- Install [Git](https://git-scm.com/) on your machine.

# Git and Github

Git is a **_fast_**, **_scalable_**, **_distributed_** revision control system with an unusually rich command set that provides both high-level operations and full access to internals.

In layman terms, Git is used to track your code changes, mark them and manage your codebase effectively. It's a time machine and multiverse. You can go back to previous versions of code, and branch out to create variants of existing code.

It's overwhelming, I know! Follow this guide, execute commands yourself and you will gradually gain confident and understand this jargon! xd

But Git and GitHub are not same!

GitHub is a cloud-based hosting service that let's you manage Git repositores. It's is important to understand this difference between Git and GitHub. It's like a registry where you can store Git repositores and collaborate with others.

Suggested Reading:
- [About GitHub and Git](https://docs.github.com/en/get-started/start-your-journey/about-github-and-git)
- [What is Git](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F)
- [What is Git (video)](https://git-scm.com/video/what-is-git)

# Essential Git Commands
Git has a rich command set, but one doesn't require to learn all of them. Understanding the most essential commands are enough to get going with Git. We will cover essential commands in this guide with examples.

## 1. `git init`

Open terminal in your machine, and create a new directory named `oss-guide` and change into this directory;
```bash
mkdir oss-guide && cd oss-guide
```

To intialise a git repository in this directory run,
```bash
git init
```

![git init output](/public/git-init.png)

But wait, what's a git repository? A git repository is essentially a parent directory/folder which contains all of your code, your files, and each file's revision history.

After intialiseing the repository, create a file name `hello-world.txt` and write "Hello, World" in the file. Let's assume that this is the first version of our code.

## 2. `git add`
All the unstaged files are first required to be staged in order to commit. 
What does that mean? Assume that you are to sing a song in the next event. You practice the song days before the event, which is similar to writing code until it's ready (unstaged files). On the day of event, you wait behind the stage waiting for your performance call, which is similar to stagging files that are ready to be commited. And when you are called on stage for performance which means you've committed to perform on stage, which is equivalent to commit code.

Once you change the file, we add it to the staging area, using 
```bash
git add <file_name>
```

if you wish to add all the files that are unstaged, use
```bash
git add .
```

## 3. `git commit`
Once the files are in staged area, they are ready to be committed. A commit is a snapshot of your codebase. 
Consider you went on a trip, first you visited Europe, then America and returned back to India. The photos you captured at each destination represent a particular snapshot of your journey. For example, on 20th November you were in Europe at some place, on 24th you were in America, etc.

Each commit represents a state of your codebase at a given time with given files.

To commit all the staged files (`hello-world.txt`) run the command,
```bash
git commit -m "intializsed the project with hello world file"
```

![git commit](/public/git-commit.png)

Once you commit the changes, they are stored in the version control history. This means you can always come back to previous commits, changes branches and alter them.
The `-m` flag is for writing a commit message which is required and essential to understand the context of the commit.

## 4. `git status`
This commands shows you the status of your codebases. It shows which files are unstaged, which files are staged. 

```bash
git status
```

- Before adding the file to staging area:
![git status before adding](/public/git-status-before-add.png)

- After adding the file:
![git status after adding](/public/git-status-after-add.png)

- After commiting the file:
![git status after commit](image.png)

## 5. `git log`
This command is used to log the previous commit in codebase. This is required when reverting to previous commiting and checking out the previous commit.

```bash
git log
```
![git log](/public/git-log.png)

Each commit is identified with its unique ID, and the log provides the details of author who committed and time zones.

## 6. `git branch`
The `git branch` command lists all the branches in the repository.

## 7. `git checkout`
To switch between branches use this command,
if the branch already exists, use
```bash
git checkout <branch_name>
```

if you wish to create a new branch and checkout to the branch directly, 
```
git checkout -b <new_branch_name>
```

By default, the repository has the `main` branch which is the working branch.

Suggested Reading:
- [Git Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf) 

## 8. `git push` : Pushing repository to Github
This command is used to push your code from local repository to a remote repository, this means your code will be hosted on cloud. To contribute with multiple developers, it is required that the source code should be pushed on GitHub which acts as a single source of truth, and all the contirbute push the changes via pull requests.

Once the files are committed, we can push the commit to remote repository using:
```bash
git push origin main
```

Here `origin`, is the remote address of our repository and `main` is the branch which we are pushing.

## `git clone`

To clone any remote repository into your machine, copy the url of the repository and run the command,
```bash
git clone <url>
```

This clones all the source code into your machine and persists the commit history of the codebase.

## `git pull`
When you need to sync the changes with a remote repository and your local repository, use the command
```bash
git pull upstream <branch_name>
```

Here upstream specifices the remote repository from which we are pulling source code, if this is not set previously run the command,

```bash
git remote add upstream <url>
```

By default, `origin` specifies remote repository associated with your account and `upstream` specifies the remote repository which you've forked from. But what does forking mean? It's means making a copy of a remote repository into your account.

Open any GitHub repository and you will see a button, named _Fork_, click on it and it will create a copy of that project in your account, so that you can play around with the code without affecting the original code.

## `git merge`
When we work on a new feature, its expected to branch off from `main` into a new branch say `feature` , write the required code and then merge the new code with `main` branch.

After commiting code in `feature` branch, checkout to `main` and use the command,
```bash
git merge feature
```

Note that this means, `feature` branch is merged into `main` and not the opposite.

![git merging](/public/git-merge.png)

Suggested reading:
- [git merge docs](https://git-scm.com/docs/git-merge)

# Working Flow on Git And GitHub

![github flow](/public/github-flow.png)

1. The maintainer's pushes the code from his local repository to remote repository on Github say `mahendra/myproject` (upstream)

2. Contributors fork this repostiory into their account. This creates individual copies in accounts of all contributors.
Here, `avi/myproject`, `ram/myproject` and `palak/myproject`. (origin)

3. Contributors install the code locally using `git clone https://github.com/<contributor_username>/myproject`.

4. To make changes in the code, contributors branch off to a new feature everytime, say `feature`. They make all the changes in this branch and `commit` their changes.

5. Once the changes are committed, the code from `feature` branch is pushed to the `origin` of contributor's repo.
```bash
git push origin feature
```

Note that contributors can't directly push to the `upstream` and only to their `origin`

6. Open your fork on GitHub, and a button will appear "Pull Request", click on the button to make a PR on the upstream. Write the description of the proposed changes and raise the PR.

7. If the maintainers suggest some changes, make them in `feature` branch and push code to `origin/feature` which will be automatically updated in the PR.

8. Finally maintainers will `merge` the code from your branch into the `upstream/main`.

9. Now to sync changes in `upstream/main` with your local `origin/main`, pull the latest code using 
```bash
git pull upstream main
```

10. Then push this changes to sync your remote `origin/main` with local `origin/main` using 
```bash
git push origin main
```

# Fin

I know its too diffuclt to understand in the first go. I have been through the same confusion and frustration in the initial days, but trust me with more practice the flow will become much clearer and you won't have to look at it ever again.

Some adavanced topics like `git rebase`, need to be studied, but can't be covered in so short time span.
Hence I will recommend you to follow the resources :
- [Git docs](https://git-scm.com/docs)
- [Git Pro Book](https://git-scm.com/book/en/v2)
- [Git and Github Tutorial](https://youtu.be/apGV9Kg7ics) by Kunal Kushwaha

If you found this guide helpful, I request you to please reach out to me on my socials and provide feedback and necessary changes.

Thanks!


