# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input parameters.  The `bug.js` file shows a route handler that attempts to parse a user ID from a request parameter.  However, it fails to handle the case where the user ID is not a valid integer, which can lead to unexpected behavior or crashes. The `bugSolution.js` file provides a corrected version with proper error handling. 

## Bug
The bug lies in the lack of error handling when parsing the `userId`. If the `userId` is not a valid integer (e.g., it's a string, or contains non-numeric characters), `parseInt(userId)` will return `NaN`, and the subsequent `users.find` operation will not locate the user, resulting in a null value being assigned to user and finally the code will crash.