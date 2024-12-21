# Unhandled Promise Rejection in Async Node.js Express App

This repository demonstrates a common error in Node.js applications involving unhandled promise rejections within asynchronous functions.  The example showcases an Express.js server where an error thrown inside a `setTimeout` callback isn't properly caught, causing the application to crash silently or unexpectedly.  The solution shows how to effectively handle such errors.

## Bug

The `bug.js` file contains an Express.js server with an asynchronous route handler.  An error is intentionally thrown 50% of the time within a `setTimeout` callback.  This error isn't handled appropriately, leading to an unhandled promise rejection.

## Solution

The `bugSolution.js` file demonstrates how to properly handle the error using a `try...catch` block inside the asynchronous function or by attaching an error listener to the process using `process.on('unhandledRejection', ...)` which is a more robust way to handle the errors that are not handled by `try...catch` block

## How to reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Run `node bug.js`
4. Observe the behavior of the application (it might crash or throw an error).
5. Run `node bugSolution.js`
6. Compare the output, and you'll see how the unhandled promise rejection is avoided.