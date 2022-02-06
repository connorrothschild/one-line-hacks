---
title: Hide an element, but only visually
tags: ['CSS', 'Accessibility']
description: Allow screen readers to access invisible content
url: https://tailwindcss.com/docs/screen-readers
---

```css
position: absolute;
width: 1px;
height: 1px;
padding: 0;
margin: -1px;
overflow: hidden;
clip: rect(0, 0, 0, 0);
white-space: nowrap;
border-width: 0;
```

# Context 

Common techniques to hide elements, such as `display: hidden`, will also hide the element from screen readers. 

In the event that you'd still like screen readers to be able to access the content, the above snippet will hide an element *visually* but not from assistive technologies. (In Tailwind, use the [`sr-only` class](https://tailwindcss.com/docs/screen-readers).)