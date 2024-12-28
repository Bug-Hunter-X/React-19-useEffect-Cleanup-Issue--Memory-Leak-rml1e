# React 19 useEffect Cleanup Issue: Memory Leak
This repository demonstrates a common mistake in React's useEffect hook: forgetting to include a cleanup function to prevent memory leaks.  Specifically, this example shows how using setInterval without proper cleanup can lead to continued counter updates even after the component is unmounted.

## Problem
The `MyComponent` uses `setInterval` to update a counter every second. However, it's missing the `return` statement within `useEffect` that's crucial for clearing the interval when the component unmounts. This results in a memory leak and unexpected behavior. 

## Solution
The solution involves adding a `return` statement to the `useEffect` function which calls `clearInterval` with the interval ID. This ensures that the interval is cleared when the component is unmounted preventing further updates.