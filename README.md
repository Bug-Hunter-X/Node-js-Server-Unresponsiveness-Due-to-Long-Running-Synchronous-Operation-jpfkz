# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a server becomes unresponsive due to a long-running synchronous operation within the request handler.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original code performs a CPU-intensive task synchronously. This blocks the event loop, preventing Node.js from handling other requests.  The server appears to hang, and clients experience slow response times or timeouts.

## Solution

The solution involves refactoring the code to use asynchronous operations or offloading the task to a worker thread. The example uses asynchronous operations using `setTimeout` to simulate long-running tasks which do not block the event loop.