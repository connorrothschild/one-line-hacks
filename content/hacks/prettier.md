---
title: Format all files using Prettier
tags: ['Command Line', 'VS Code']
description: Format all files with a given extension using Prettier on the command line.
url: https://prettier.io/docs/en/cli.html
---

```shell
prettier --write "**/*.vue"
```

# Context 

When you want to run `prettier` on all files in a given directory, and your VSCode extension isn't working (thanks M1?).

Where `.vue` matches the file extension you want to target and format.