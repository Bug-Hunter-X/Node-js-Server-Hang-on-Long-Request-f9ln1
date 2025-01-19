# Node.js Server Hang on Long Request

This repository demonstrates a common issue in Node.js where a long-running request blocks the event loop, causing the server to appear unresponsive.  The `server.js` file shows a simple HTTP server with a request handler that simulates a long-running task.  The solution, provided in `serverSolution.js`, uses asynchronous operations to prevent the event loop from being blocked.

## How to reproduce

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `node server.js`.
4. Send multiple requests to `http://localhost:3000`.  Observe that after a few requests the server stops responding to new requests.

## Solution

The solution involves using asynchronous operations to handle long-running tasks outside of the main event loop.  This ensures that other events and requests can still be processed.
