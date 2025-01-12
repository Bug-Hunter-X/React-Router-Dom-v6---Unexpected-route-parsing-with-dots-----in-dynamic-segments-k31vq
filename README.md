# React Router Dom v6 - Unexpected route parsing with dots (.) in dynamic segments

This repository demonstrates an unexpected behavior in React Router Dom v6 when navigating to routes with dynamic segments that contain dots (.) in the URL.  The issue arises when a dynamic segment such as `:userId` contains a dot, causing the route to be parsed incorrectly and the component to fail to render.

## Bug Description
The route `/users/john.doe` is expected to match the `Route` with path `/users/:userId` and render the `User` component. However, the current implementation fails to do so, instead potentially rendering nothing or an error.

## Reproduction Steps
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Navigate to `/users/john.doe` in your browser.

The User component will not render as expected.

## Solution
The solution is to use a more accurate regular expression within the route path to capture the dynamic segments correctly.

## Note
This bug is specific to React Router v6 and how it handles dots within dynamic route segments.  Earlier versions of React Router might not experience the same issue.