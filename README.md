# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by modifying the state variable within the effect's callback function without proper dependency management. 

The `bug.js` file contains the erroneous code.  The `bugSolution.js` file provides the corrected implementation.

## Problem

The issue arises from incorrectly using the `useEffect` hook. When the `setCount` function updates the `count` variable within the `useEffect` callback (without any conditional break or asynchronous operations), this creates a loop. Each update triggers a re-render, which then triggers the `useEffect` again. This process repeats indefinitely, leading to a browser crash or significant performance degradation.

## Solution

The correct implementation uses the previous state as a reference to prevent the infinite loop. For example, by using the functional update version of `setCount` or by introducing a conditional logic to escape the infinite loop.