# Evergreen Quote: Vision Brief

> Copy this file into `delivery-leadership-package/vision-brief.md` in your repo and fill it in. Target length: 1 page (~300 words). Write for a Liberty Mutual VP who has 90 seconds.

## Product
**Name:** Evergreen Insurance Quote (the launch: full-stack delivery)
**Delivery week:** Final
**Delivery Lead:** Kristen Marturano
**Engineering team (represented by):** [(https://github.com/asc1-student06/evergreen-quote-launch)
**GitHub Project board:** (https://github.com/users/asc1-student06/projects/8/views/1?system_template=kanban)

## Who is the customer?
People shopping for auto, home, or life insurance on the Evergreen site who want an instant monthly prices, plus partner sites that request quotes through the API.

## What pain does Evergreen Quote remove?
Today the page estimates and the service remembers, but they've never connected. A customer can get an estimate, but a saved quote disappears on reload, and the page shows sample data instead of real quotes. Wiring them together means one source of truth: every quote is priced by the server, saved to the database, and still there when the customer comes back.

## What does "good" look like at end of the week?
- The React app shows real quotes from the API, and a saved qupte survives a reload.
- The estimate and the saved premium match (one set of rates, with the server as the source of truth).
- The landing page's launch banner and links are set, and "Get your quote" opens the app.
- The API runs in a container (2.0) and as 3 replicas on a local Kubernetes cluster
- It's merged to main through a reviewed PR with both CI jobs green.

## What are we explicitly NOT doing this week?
- Writing new features or refactoring the team's code (assembly, not authoring).
- Renters coverage
- A required cloud deploy (EKS only if the sponsor opens Thursday's window).
- Logins, payments, or binding policies.
- 
- 

## How will we know if it worked?
- Persistence: 1 of 1 saved quotes still there after a reload. Today its 0.
- One price: the estimate equals the saved premium for auto/ age 35 /$50,000. Expect $450 = $450. Today its $425 vs $450.
- Quality Gates: 2 of 2 CI jobs green on the merge and 7 of 7 API tests passing.
- Resilience: 3 of 3 API pods running on the cluster, with the unchanged app saving through them.
- 
