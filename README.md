# Unexpected useEffect Behavior in React 19

This repository demonstrates a potential issue with the `useEffect` hook in React 19 where it might trigger more often than expected, leading to performance problems or unexpected side effects.

## Description

The `useEffect` hook in React is designed to perform side effects after a component renders.  However, if the dependency array is incorrect, or if the component re-renders without changes to the dependencies, it might trigger unintentionally.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console logs and the component's behavior.  The `useEffect` hook will print the current count to the console after every render which can be inefficient if the count doesn't change.

## Solution

The solution involves carefully defining the dependency array. In this case, the `useEffect` hook only needs to run when `count` changes, so the dependency array should only include `count`.