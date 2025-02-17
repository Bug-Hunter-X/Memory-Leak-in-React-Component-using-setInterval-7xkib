# React setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook, resulting in a memory leak.  The solution shows how to properly implement the cleanup function to avoid this issue.

## Problem

The `bug.js` file contains a React component that uses `setInterval` to increment a counter every second.  However, it fails to include a cleanup function to stop the interval when the component unmounts.  This leads to the interval continuing to run indefinitely, even after the component is removed from the DOM, causing a memory leak.

## Solution

The `bugSolution.js` file demonstrates the correct approach.  A cleanup function is returned from `useEffect`, which uses `clearInterval` to stop the interval when the component unmounts. This prevents the memory leak.