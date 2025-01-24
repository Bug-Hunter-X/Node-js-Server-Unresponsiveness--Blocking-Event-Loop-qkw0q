# Node.js Server Unresponsiveness: Blocking Event Loop

This repository demonstrates a common Node.js issue: blocking the event loop with a long-running synchronous operation.  The server becomes unresponsive while handling a single request. 

The `server.js` file shows the problematic code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem
The original code uses a `while` loop to simulate a long-running task, completely blocking the event loop for 5 seconds.  During this time, the server cannot accept or process any new requests.  This leads to high CPU usage and an unresponsive server.

## Solution
The solution utilizes asynchronous operations (e.g., `setTimeout`) to avoid blocking the event loop.  Asynchronous code allows other events to be processed concurrently, keeping the server responsive.