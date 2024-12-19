# Express.js Unhandled Error: Invalid User ID

This repository demonstrates a common error in Express.js route handlers: insufficient error handling for invalid input. Specifically, the code lacks checks for non-numeric user IDs, potentially leading to crashes or unexpected behavior.

## Bug Report

The `bug.js` file contains the problematic code.  It attempts to parse the user ID from the request parameters as an integer but does not handle the case where the ID is not a valid integer.  This can result in unexpected errors if the ID is not a number or is otherwise malformed.

## Solution

The `bugSolution.js` file provides a corrected version of the code.  It includes explicit checks to ensure the user ID is a valid integer before attempting to use it. This prevents crashes and ensures a more robust and predictable application behavior.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install` to install Express.js.
3. Run `node bug.js`.
4. Send a request to `/users/abc` (or any other non-numeric ID). The server will likely crash or return an unexpected error.

## How the solution addresses the bug

The solution uses `isNaN` to check if the parsed ID is a number and provides a clear error response (400 Bad Request) if the ID is invalid. This makes the application more robust and user-friendly. 