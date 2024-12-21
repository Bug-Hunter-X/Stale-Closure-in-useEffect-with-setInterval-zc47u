# Stale Closure in useEffect with setInterval

This repository demonstrates a common error in React applications involving stale closures within the `useEffect` hook when used with `setInterval`.  The issue arises because the variable referenced within the `setInterval` callback is captured at the time the `useEffect` is initially executed, not updated as the component re-renders. 

## Bug
The provided code demonstrates the issue. `count` value will remain 0 even though the component re-renders. 

## Solution
The solution uses a `useRef` to capture the current value of `count`, thereby avoiding the stale closure problem.  This ensures that the latest value of `count` is used inside the `setInterval` callback.
