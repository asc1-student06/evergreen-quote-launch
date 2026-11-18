# Delivery Goal: Evergreen Quote

> Copy this file into `delivery-leadership-package/delivery-goal.md`. One sentence. Read it back to yourself. Then to your pair. Then to someone who wasn't in the room. If they can repeat it, it's good.

## Goal

By Thursday EOD, the wired Evergreen Quote app saves quotes that survive a reload, the containerized API (2.0) has run as 3 replicas on the local cluster, and the launch is merged to main via a reviewed PR with both CI jobs green. 

## "Done" looks like

- The quote page loads its recent quotes from the API, and a saved quote survives a reload.
- The estimate on screen and the saved premium agree, at the launch rates.
- `npm test` (API) and `npm run type-check` + `npm run build` (client) pass; both CI jobs on the merge commit are **green**.
- The containerized API serves the wired app, and the cluster demo shows three API pods behind one Service.
- The landing page carries the launch banner and points at the app.
- A reviewed PR is merged, branch deleted.
- `delivery-leadership-package/` is complete and committed.

## Out of scope (this week)

- Writing new features or refactoring the team's code (assembly, not authoring).
- Renters coverage
- A required cloud deploy (EKS only if the sponsor opens Thursday's window).
- Logins, payments, or binding policies.