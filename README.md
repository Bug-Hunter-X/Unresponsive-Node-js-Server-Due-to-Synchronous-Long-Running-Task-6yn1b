# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js applications: an unresponsive server caused by a long-running synchronous operation that blocks the event loop.  The `bug.js` file contains code that simulates this problem.  The `bugSolution.js` file offers a solution using asynchronous operations.

## Problem

The server in `bug.js` performs a 5-second synchronous CPU-bound task within the request handler.  During this time, the server cannot handle any other requests, leading to unresponsiveness.

## Solution

The `bugSolution.js` file addresses the issue by offloading the long-running task to an asynchronous operation (though a more sophisticated approach would use a worker thread or task queue for CPU-bound tasks).  This prevents blocking the event loop and maintains server responsiveness.

## How to run

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `node bug.js` to see the unresponsive server.
4. Run `node bugSolution.js` to see the improved, responsive server.