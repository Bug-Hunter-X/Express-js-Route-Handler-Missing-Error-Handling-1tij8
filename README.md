# Express.js Route Handler Missing Error Handling

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, the provided code lacks error handling for cases where the user ID is not a valid number.

## Bug

The `bug.js` file contains an Express.js route handler that fetches a user based on their ID.  If the ID is not a number, the `parseInt(userId)` function will return `NaN`, causing the `.find()` method to fail silently or throw an error, leading to a 500 Internal Server Error instead of a more graceful 404 Not Found response.

## Solution

The `bugSolution.js` file provides a corrected version of the route handler. It includes explicit error handling to check if the parsed ID is a valid number using `isNaN()`, returning a 404 status code if the ID is invalid or the user is not found.