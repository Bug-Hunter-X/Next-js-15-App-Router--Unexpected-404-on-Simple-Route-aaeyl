# Next.js 15 App Router: Unexpected 404 on Simple Route

This repository demonstrates an unexpected 404 error encountered in a Next.js 15 App Router application with a seemingly simple route.

The issue is that even the most basic page (`pages/index.js`) returns a 404 Not Found error when running `npm run dev`.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Observe the 404 error in the browser.

## Potential Causes

This error could arise from several factors within a Next.js 15 App Router setup:

* **Incorrect file naming or placement:** Next.js 15 relies on the file structure and naming conventions for routing.  A slight mistake can lead to unexpected 404 errors.
* **Conflicting Middleware:** Middleware can alter the behavior and routing of requests. A bug within the middleware could be redirecting requests incorrectly.
* **Server-side issues:** If the problem only occurs in the development environment, this might indicate a problem with your local development server configuration.
* **Unexpected behavior in the App Router:** Since this is a relatively new feature in Next.js 15, there might be quirks or unexpected behaviors not yet widely documented.

## Solution

This specific example is often caused by having both `pages` and `app` directories simultaneously. Next.js will use only the `app` directory for routing by default and will ignore the `pages` directory unless configured to use it. A solution is to remove the `pages` directory if not needed.