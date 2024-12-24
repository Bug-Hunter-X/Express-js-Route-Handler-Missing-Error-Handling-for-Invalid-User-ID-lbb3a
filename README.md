# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, the provided code fails to handle cases where the user ID is not a valid integer.

## Bug

The `bug.js` file contains the faulty code.  The route handler attempts to parse the `userId` as an integer and use it to find a user.  If `userId` is not a valid integer (e.g., it's a string, or contains non-numeric characters),  `parseInt(userId)` will return `NaN`, leading to a failure to find the user and potential crashes or unexpected behavior depending on the implementation of the `users` array.

## Solution

The `bugSolution.js` file shows how to fix the bug. The solution adds input validation to ensure that `userId` is a valid integer before attempting to find the user.  If the ID is invalid, a proper HTTP error response (400 Bad Request) is returned.