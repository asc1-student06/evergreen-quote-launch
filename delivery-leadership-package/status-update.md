# Stakeholder Status Update: Evergreen Quote

> Copy to `delivery-leadership-package/status-update.md`. Send it (i.e., paste it in the cohort channel) at the end of the day an inject lands. Target length: ~150 words.

**To:** Priya Ramananathan
**From:** Kristen Marturano, Delivery Lead
**Date:** 11/17/26

## What shipped today

- the React app is now wired to the API. it shows real quotes from the database, and for the first time in the program a saved quote survives a reload. The type-check caught a mismtatch between the two systems before any customer would have, and the team's one-line fix is in. Estimates and saved prices now agree at your standardized rates. The launch title, banner, and links are set, and GraphQL is mounted.
- 

## What slipped (and why)

- Schedule: I started the week about a day behind. That's recovered: Days 1 and 2 were completed today. On Day 1, the starter kit was again missing its hidden config files (.gitignore, api/.env, client/.env). I rebuilt them from the code and the npm install had quietly changed the teams lock files, so I restored those. These issues cost setup time but didn't affect the product.
- Form defualt to life: routed, not done. It's in the engineering team's quote logic, which every estimate runs through. I've sent it to the client team with Fridays launch date attached. If they can't review it safely by Weds EOD it becomes the first change after launch.
- Renters: deferred to next round by hoice. It now spans both validation systems (the app and databases) plus rates on both sides, and it needs a renters rate from you.

## What's next (tomorrow)

- Containerize the API as evergreen-quote-api:2.0
- Run the stack on the local Kubernetes cluster (3 API replicas plus MongoDB) with the app talking to it unchanged
- Enable the two-job CI pipeline (API tests plus the client type-check and build)
- Oversee one Copilot-assisted step, and make the go/no-go call for Friday's demo.
## What I need from you

1) confirm the life-first hero wording by 10:30am Weds. 
2) the client team's yes or no on the form default by Weds EOD
3) a renters rate decision for next round
