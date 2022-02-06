---
title: Prevent fixed navbar from overlapping hash-navigated content
tags: ['CSS']
description: Apply scroll padding to your entire webpage
url: https://webplatform.news/issues/2019-03-19#the-css-scroll-padding-property-adjusts-a-scroll-container-s-optimal-viewing-region
---

```css
html {
  scroll-padding-top: 70px; /* height of sticky header */
}
```

# Context 

When your navbar is fixed (e.g. attached to the top of the webpage at all times), it takes up no space on the page. This means that it overlaps content below it; when navigating to subsections on your webpage, e.g. through hash-navigation, this means that the content below the navbar will be obscured.

`scroll-padding-top` fixes this problem. As explained on Web Platform News:

> For example, websites with sticky headers can apply a matching scroll padding to the top of the page to ensure that scroll targets (e.g., section headings) aren’t concealed by the header after certain scroll operations (anchor scrolling, scrollIntoView method, etc.).