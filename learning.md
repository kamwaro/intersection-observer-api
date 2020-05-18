-- The Intersection Observer API provides a way to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's viewport.

### Reasons intersection information is needed:

1. Lazy-loading of images or other content as a page is scrolled.
2. Implementing "infinite scrolling" websites, where more and more content is loaded and rendered as you scroll, so that the user doesn't have to flip through pages.
3. Reporting of visibility of advertisements in order to calculate ad revenues.
4. Deciding whether or not to perform tasks or animation processes based on whether or not the user will see the result.

-- The Intersection Observer API covers the common use case, "If they intersect by somewhere around N%, I need to do something."

## Intersection OBserver Concepts and Usage:

- The intersection observer api allows you to configure a callback that is called:
  1.) Whenever one element, called the 'target', intersects either the device viewport or a specified element; for the purpose of this API, this is called the root element

* The degree of intersection between the target element and its root is the intersection ratio.
  This is a representation of the percentage of the target element which is visible as a value;
* This is a representation of the percentage of the target element which is visibile as a value between 0.0 and 1.0

### Creating an intersection observer...

- Its created by calling its constructor and passing it a callback function to be run whenever a threshold is crossed in one direction or the other:

let options = {

        root: document.querySelector('#scrollArea'),
        rootMargin: '0px',
        threshold: 1.0

}

let observer = new IntersectionObserver(callback, options)

### Intersection observer options

- The options object passed into the
