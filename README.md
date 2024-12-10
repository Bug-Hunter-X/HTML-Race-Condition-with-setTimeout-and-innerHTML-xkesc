# Uncommon HTML Bug: Race Condition with setTimeout and innerHTML

This repository demonstrates a subtle race condition that can occur in HTML when using `setTimeout` to update the `innerHTML` of an element that is also being modified. 

## Bug Description:
The `bug.html` file shows a simple example where a button click clears a div's content and then, after a delay, attempts to add new content.  The race condition arises because the `innerHTML` is set to an empty string synchronously, before the `setTimeout` callback has a chance to execute. If the div element is removed, an error occurs because the target element no longer exists.

## Solution:
The `bugSolution.html` demonstrates how to fix this issue by using a flag or state variable to control the update of the innerHTML, preventing the race condition.