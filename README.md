# React setInterval Memory Leak
This example demonstrates a common error in React components: using `setInterval` within `useEffect` without proper cleanup. This leads to memory leaks because the interval continues running even after the component unmounts.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks a cleanup function to stop the interval when the component is unmounted. This causes a memory leak because the interval continues to run indefinitely. 

## Solution
The `bugSolution.js` file demonstrates the correct way to use `setInterval` within `useEffect`.  A cleanup function is returned from the `useEffect` callback, which uses `clearInterval` to stop the interval before the component unmounts.