# Uncommon HTML Bug: Incorrect innerHTML Modification

This repository demonstrates an uncommon bug related to manipulating the innerHTML property of a DOM element.  The bug arises when attempting to modify the innerHTML of an element that doesn't yet exist in the DOM tree.  This can lead to unexpected behavior, often silently failing without any error messages in the console.

The bug and its solution are contained within the `bug.html` and `bugSolution.html` files, respectively.

## Bug Description
The bug occurs because the JavaScript code attempts to access and modify the `innerHTML` of the element with the id `myDiv` before the browser has fully parsed and rendered the HTML.  This leads to an error without a visible message.

## Solution
The solution involves ensuring that the script that modifies the `innerHTML` runs *after* the element with id `myDiv` has been rendered.  This can be done by placing the script at the end of the HTML `<body>` or by wrapping the modification code in a DOMContentLoaded event listener.