# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using the `setInterval` function within a React `useEffect` hook, leading to a memory leak.  The problem stems from the absence of a cleanup function to stop the interval when the component unmounts or updates.

## Bug
The `bug.js` file contains the flawed component. The `setInterval` function is called without proper cleanup, causing the interval to continue even after the component is no longer needed.

## Solution
The `bugSolution.js` file provides the corrected implementation. The `useEffect` hook now includes a return function that uses `clearInterval` to stop the interval when the component is unmounted or when the dependencies change.