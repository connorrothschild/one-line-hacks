---
title: Untrack tracked files
tags: ['Git']
description: Untrack files already added to git repository based on .gitignore
url: https://www.codeblocq.com/2016/01/Untrack-files-already-added-to-git-repository-based-on-gitignore/
---

```bash
git rm -r --cached .
git add .
git commit -m ".gitignore fix"
```

# Context 

Ever added a file to `.gitignore` just to visit GitHub/Lab and realize its still there? It was probably never untracked. Doing the above will remove all files from git, readd them (with the newly ignored file), and recommit.