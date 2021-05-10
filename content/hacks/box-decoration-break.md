---
title: Make CSS styling span multiple lines
tags: ['CSS']
description: Using <code>box-decoration-break</code> to prevent abrupt style interruptions
url: https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break
---

```css
-webkit-box-decoration-break: clone;
box-decoration-break: clone;
```

# Context 

Prevents styling applied to text to break abruptly at the end of a line. The above will force it to 'finish' its style (e.g., round a border and finish padding) at the end of the line, and start again at the next line.

An example **without**: <span style='background: steelblue; color: white; padding: 1px 3px; border-radius: 5px;'>Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum </span>

An example **with**: <span style='box-decoration-break: clone; background: steelblue; color: white; padding: 1px 3px; border-radius: 5px;'>Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum Lorem ipsum </span>