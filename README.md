# Node.js Server Hang Issue

This repository demonstrates a common issue in Node.js applications where a long-running task within a request handler can cause the server to appear unresponsive or hang.  The provided code simulates this scenario and showcases a solution to address it.

## Problem

The `server.js` file contains a simple Express.js server.  However, the request handler for the root path introduces a 5-second delay using `setTimeout`.  In production environments, this delay might represent a long database query, file I/O operation, or other time-consuming task. This can lead to the following problems:

* **Unresponsiveness:**  Clients making requests will experience significant delays, potentially leading to timeouts.
* **Resource Exhaustion:**  If many requests are made concurrently while each one is waiting 5 seconds to resolve the server might crash
* **Poor User Experience:**  Users will perceive the application as slow or broken.

## Solution

The `serverSolution.js` file provides a solution using asynchronous operations. By using Promises or async/await we can prevent the server from blocking and allows it to handle other requests without issues.

## How to Run

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` to install the dependencies.
4. Run `node server.js` to start the problematic server.
5. Run `node serverSolution.js` to start the improved server.

## Contributing

Contributions are welcome!  If you have any suggestions or improvements, please submit a pull request.