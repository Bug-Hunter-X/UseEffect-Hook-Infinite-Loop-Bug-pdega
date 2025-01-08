# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications where the `useEffect` hook inadvertently creates an infinite loop. The bug arises from incorrectly specifying the dependency array, causing the effect to re-run after every render, even when the state variable it depends on isn't actually changing.

## Bug Description
The `useEffect` hook, while powerful, requires careful attention to its dependency array.  If the effect modifies a state variable it also depends upon, and that variable isn't listed in the dependencies, the effect will trigger repeatedly, leading to an infinite rendering loop and potentially crashing the application.

## How to Reproduce
1. Clone this repository.
2. Navigate to the `bug.js` file.
3. Run `npm start` to launch the application in development mode.
4. Observe the console for continuously logging the count. The application might crash or become unresponsive due to an infinite loop.

## Solution
The solution lies in correctly specifying the dependency array in the `useEffect` hook. We need to ensure that the effect only runs when the state variable(s) it depends on have actually changed.