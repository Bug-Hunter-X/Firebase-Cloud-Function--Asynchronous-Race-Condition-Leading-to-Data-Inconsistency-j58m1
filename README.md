# Firebase Cloud Function Asynchronous Race Condition

This repository demonstrates a common issue in Firebase Cloud Functions involving asynchronous operations and race conditions. The function attempts to access data from the Realtime Database before it's completely written, leading to inconsistent or undefined values.  The solution showcases the proper use of promises and transactions to guarantee data integrity.

## Problem

The `bug.js` file contains a Firebase Cloud Function that suffers from a race condition.  It attempts to read data asynchronously before the data it relies on is fully written to the database, causing unpredictable behavior.

## Solution

The `bugSolution.js` file provides a corrected version of the function. It uses promises and waits for data to be written, ensuring data consistency.  It utilizes transactions to atomically update related data, preventing race conditions.

## How to run

1.  Clone this repository.
2.  Install dependencies: `npm install`
3.  Configure your Firebase project.
4.  Deploy the functions: `firebase deploy --only functions`

This example shows how crucial it is to handle asynchronous operations carefully when working with Firebase.