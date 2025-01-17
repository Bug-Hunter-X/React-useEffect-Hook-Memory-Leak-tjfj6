# React useEffect Hook Memory Leak

This repository demonstrates a common mistake in using React's `useEffect` hook: forgetting the return statement for cleanup. This can lead to memory leaks and unexpected behavior.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version.

## Problem

The original code updates the document title on every click.  However, it lacks a cleanup function in the `useEffect` return statement.  This means that on every render, a new listener is added, without removing the previous one. This leads to multiple listeners accumulating and to memory leaks.