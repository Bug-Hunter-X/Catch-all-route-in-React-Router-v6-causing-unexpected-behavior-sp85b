# React Router v6 Catch-all Route Issue

This repository demonstrates a subtle issue with the catch-all route (`path="/*"`) in React Router v6.  The issue arises when this route is placed after more specific routes.  In some cases, it may unexpectedly prevent other routes from matching correctly, even when the URL should match one of the more specific routes.

## Steps to reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Navigate to `/about`.  The 'Not Found' component should be rendered.

## Solution

The solution involves correctly ordering the routes within the `Routes` component.  The catch-all route (`/*`) should always be placed *last*.  If not, it will override any more specific routes.

See `AppSolution.js` for a corrected version of the code.