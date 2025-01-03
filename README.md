# React Native Unhandled JS Exception: Cannot read properties of undefined (reading 'name')

This repository demonstrates a common error in React Native applications:  "Unhandled JS Exception: Cannot read properties of undefined (reading 'name')".  This error arises when attempting to access a property of an object before it has been fully loaded or when the object is null or undefined.

The `bug.js` file shows the erroneous code, while `bugSolution.js` provides the corrected implementation.

## Problem

The problem lies in accessing `data.name` before the asynchronous `fetch` call in `bug.js` has completed and populated the `data` state with data.  When the component initially renders, `data` is `null`, leading to the error.

## Solution

The solution in `bugSolution.js` involves using optional chaining (`?.`) and nullish coalescing (`??`) to safely access the `name` property.  Optional chaining prevents the error if `data` is `null` or `undefined`, and nullish coalescing provides a default value if `data.name` is nullish.