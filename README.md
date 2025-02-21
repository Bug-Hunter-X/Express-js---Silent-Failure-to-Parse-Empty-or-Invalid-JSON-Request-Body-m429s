# Express.js Silent JSON Parsing Failure

This repository demonstrates a subtle bug in an Express.js application where attempts to parse empty or invalid JSON request bodies fail silently.  The server doesn't provide helpful error messages, making debugging challenging.

## The Problem

The `express.json()` middleware is expected to parse incoming JSON requests. However, if the request body is empty or contains malformed JSON, it won't throw an error. Instead, it logs an empty object `{}` to the console, leaving developers unaware of the issue.

## Solution

The solution involves implementing custom error handling to catch and report parsing errors. This approach ensures that the application gracefully handles invalid JSON input and provides informative error messages.