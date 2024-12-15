# JavaScript Loose Comparison Bug
This repository demonstrates a subtle bug in JavaScript's loose comparison (==) operator when dealing with NaN (Not a Number) and positive/negative zero (+0/-0).

## The Problem
JavaScript's loose comparison (==) does not follow the expected rules of equality for NaN and +0/-0:

* `NaN == NaN` evaluates to `false` (NaN is never equal to itself).
* `+0 == -0` evaluates to `true` (positive and negative zero are considered equal).

This behavior can be a source of unexpected results and difficult-to-debug errors in your code.

## How to Reproduce
1. Clone this repository.
2. Open `bug.js` and run it in a JavaScript environment (e.g., Node.js, browser's console).
3. Observe the unexpected results.

## The Solution
Use strict equality (===) instead of loose equality (==) to avoid this issue.  Strict equality correctly distinguishes between NaN and numbers, and between +0 and -0.  See `bugSolution.js` for a corrected version of the code.

## Additional Notes
Always use strict equality (===) unless you have a specific reason for using loose equality.  Strict equality leads to more predictable and less error-prone code.  Understanding the peculiarities of NaN and zero in JavaScript is essential for writing robust and reliable JavaScript applications.