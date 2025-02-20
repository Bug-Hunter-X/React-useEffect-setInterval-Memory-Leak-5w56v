# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to clear the interval when the component unmounts. This leads to a memory leak.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to clear the interval using `clearInterval` when the component unmounts, resulting in a continuous interval even after the component is no longer rendered. This causes a memory leak, consuming resources unnecessarily.

## Solution
The `bugSolution.js` file provides a corrected version. It stores the interval ID in a `ref` and uses `useEffect`'s cleanup function to clear the interval when the component unmounts. This ensures that no memory leaks occur.