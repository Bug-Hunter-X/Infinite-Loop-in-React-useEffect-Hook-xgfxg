# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications: an infinite loop caused by improper dependency array handling within the `useEffect` hook.

## Bug Description
The `MyComponent` function uses `useEffect` to increment a counter.  However, the dependency array is empty (`[]`), which means the effect runs after every render.  Because the effect modifies the state (`setCount`), this creates an infinite loop.

## Solution
The solution involves correctly specifying the dependencies in the useEffect's dependency array.  If the effect depends on the `count` state, it should be included in the array. If it doesn't depend on any state, an empty array is still correct and will not cause an infinite loop.