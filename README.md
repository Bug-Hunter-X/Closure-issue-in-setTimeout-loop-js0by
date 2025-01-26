# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue that arises when using `setTimeout` within a loop. The problem stems from how JavaScript handles closures and variable scoping.

## Bug Description

The `bug.js` file contains a function `myFunction` that uses a `for` loop to schedule multiple calls to `setTimeout`. The intention is to log the value of `i` for each iteration. However, due to the way closures work in JavaScript, the logged value of `i` will be the final value of the loop (10) rather than the values 0 through 9.

## Solution

The `bugSolution.js` file provides a solution that correctly captures the value of `i` using an immediately invoked function expression (IIFE).

## How to Reproduce the Bug

1. Clone this repository.
2. Open `bug.js` in your preferred JavaScript environment.
3. Run the `myFunction` function.
4. Observe that the console logs the value 10 ten times.

## How the Solution Works

The solution uses an IIFE to create a new scope for each iteration of the loop. This ensures that the value of `i` is captured at the time the `setTimeout` callback is created, rather than when it is executed.