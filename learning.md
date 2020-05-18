-- The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's viewport.

### Reasons intersection information is needed:

1. Lazy-loading of images or other content as a page is scrolled.
2. Implementing "infinite scrolling" websites, where more and more content is loaded and rendered as you scroll, so that the user doesn't have to flip through pages.
3. Reporting of visibility of advertisements in order to calculate ad revenues.
4. Deciding whether or not to perform tasks or animation processes based on whether or not the user will see the result.

-- The Intersection Observer API covers the common use case, "If they intersect by somewhere around N%, I need to do something."
