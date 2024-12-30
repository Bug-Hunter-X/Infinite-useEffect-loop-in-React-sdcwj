# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving an infinite loop within the `useEffect` hook. The component continuously updates, leading to performance degradation and an overflowing console.

## Bug Description

The `useEffect` hook, without proper dependency array handling, triggers repeatedly after every render. This can occur when the effect's logic directly or indirectly modifies state or props that are within its dependencies.  In this case, the effect logs the count to the console which is continuously updated within the component. This leads to a continuous loop of rendering and effect execution.

## Solution

The solution involves correctly specifying the dependencies array in `useEffect`.  By including `count` in the dependency array, the effect only runs when the value of `count` changes. If no dependencies are needed, it's possible to pass an empty array, which results in the effect firing only once after the component mounts.