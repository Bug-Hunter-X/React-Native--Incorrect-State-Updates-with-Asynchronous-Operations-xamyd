# React Native: Incorrect State Updates with Asynchronous Operations

This repository demonstrates a common issue in React Native development where asynchronous operations lead to incorrect state updates due to stale closures. The problem occurs when using methods like `setTimeout` or `fetch` within a `setState` callback.

## Problem Description

When using asynchronous functions inside `setState`, the closure used within the asynchronous function captures the initial value of the state variable. This can result in the state value not being updated correctly, leading to unexpected behavior.

## Solution

The solution involves ensuring that the state is updated correctly using functional updates with the `prevCount` value inside the asynchronous operation. This ensures that you're always working with the latest state value and prevents stale closures.  We also demonstrate the use of `useRef` for tracking values that don't necessarily trigger re-renders.