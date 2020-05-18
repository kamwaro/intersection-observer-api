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
* This is a representation of the percentage of the target element which is visible as a value between 0.0 and 1.0

### Creating an intersection observer...

- Its created by calling its constructor and passing it a callback function to be run whenever a threshold is crossed in one direction or the other:

let options = {

        root: document.querySelector('#scrollArea'),
        rootMargin: '0px',
        threshold: 1.0

}

let observer = new IntersectionObserver(callback, options)

## Intersection observer options

- The options object passed into the IntersectionObserver() constructor lets you control the circumstances under which the observer's callback is invoked. It has the following fields:

##### root

    - The element that is used as the viewport for checking visibilty of the target. Must be the ancestor of the target. I t defaults to the browser viewport if not specified or if `null`.

##### rootMargin

    - Margin around the root. Can have values similar to the CSS margin property e.g "10px 20px 30px 40px(top right bottom and left)". The values can be percentages. This set of values serves to grow or shrink each side of the root element's bounding box before computing intersections. Defaults to all zeros.

##### threshold

    - Either a single number or an array of numbers which indicate at what percentage of the target's visibility the observer's callback should be executed.
    - If you only want to detect when  visibility passes the 50% mark, you can use a value of 0.5. If you want the callback to run every time the visiblity passes another 25%, you would specify the array [0,0.25,0.5,0.75,1].
    The default is 0, meaning as soon as even one pixel is visible, the callback will be run.
    - A value of 1.0 means that the threshold isn't considered passed until every pixel is visible.

##### Targeting an element to be observed

- Once you have created the observer, you need to give it a target element to watch:

=> let target = document.querySelector('#listItem');
observer.observe(target)

- Whenever the target meets a threshold specified for the IntersectionObserver, the callback is invoked. The callback receives a list of IntersectionObserverEntry objects and the observer:
