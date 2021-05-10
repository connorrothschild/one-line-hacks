---
title: Initialize a Git Repository from an Existing Project
tags: ['CSS']
description: For when you've already started a project and want to start VC late
url: https://kbroman.org/github_tutorial/pages/init.html
---

```shell
git init
git add .
git commit -m "init"

## Setup on GitHub/GitLab, etc.
git remote add origin git@github.com:<username/new_repo>
git push -u origin master
```

# Context 

Super simple. Basically, rather than *begin* your project with git initialized/version control set up, you want to do so in an existing directory. 