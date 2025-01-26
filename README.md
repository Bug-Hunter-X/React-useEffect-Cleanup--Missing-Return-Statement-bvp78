# React useEffect Cleanup: Missing Return Statement

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include a return statement in the cleanup function to properly clear intervals or timeouts.  This leads to memory leaks and potential performance issues.

## The Bug
The `bug.js` file contains a component with a `useEffect` hook that uses `setInterval`. However, it omits the return statement within the `useEffect` which is crucial to clear the interval when the component unmounts.  This will cause a memory leak as the interval continues infinitely.

## The Solution
The `bugSolution.js` file demonstrates the correct way to use the `useEffect` hook and ensures proper cleanup.

## How to reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to run the application.   Observe the behavior of the component. You will see the counter incrementing. Unmounting and remounting the component will show that the counter continues from where it left off, indicating that the `setInterval` is not correctly being cleared.
4. Examine the code in `bugSolution.js` to see the correct implementation, where the return statement clears the interval during unmounting.