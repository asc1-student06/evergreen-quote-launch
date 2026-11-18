# Risk Register

> Copy to `delivery-leadership-package/risk-register.md`. At least 5 rows. **No boilerplate**; your peers will grade you on whether these are real.

| # | Risk | Owner | Likelihood (L/M/H) | Impact (L/M/H) | Mitigation | Trigger to escalate |
|---|---|---|---|---|---|---|
| R1 | The data gap changed shape. The app used to be unwired; not its wired so the demo depends on a running database, and the clusters db starts empty | Kristen Marturano | H | H | Written demo plan; save demo quotes in the cluster before friday; screenshot fallback | _The app shows an empty list or errors during rehearsal |
| R2 | Rate drift can come back. Premium math lives in 2 places (the clients estimate and the API saved price) | Client + Platform teams | M | H |  |Aligned to the APIs rates today (the server is the source of truth) decision memo on long term fix  | Estimate does not equal saved premium for any quote
| R3 | Starter kit arrived without hidden config files, the second time in 2 phases | Kristen Marturano + Instructor | H | M | Rebuilt them from the codes own defaults on day 1 | The service won't start or node_modules shows up in git status |
| R4 | npm install silently changed the teams lock files, so CI could test diff dependencies than the teams pinned | Engineering teams | M | M | Restored the lock files with git restore before committing | Lock files show as modified in git status before a commit |
| R5 | Launch-week change requests to shared code  | Kristen Marturano + Sponsor | H | H | Split content (approved) from code (routed to the owning team with a date); renters deferred | The sponsor overrides a deferral, so I re-plan and name what comes out |
| R6 | Port 3000 conflicts. The dev API, the container, and weds port-forward all want the same port | Kristen Marturano  | H | L | Stop one before starting the next; recover with ss -ltnp and kill | the port status busy after kill, so I ask Fox |

## How I'll use this register

I review it at the start of each day before the check-in, and again after each inject. I update likelihood and impact as things change. For example, R1 rises on Wed when the demo moves to the clusters empty db, and R2 drops once estimates and saved prices match. I close risks when their mitigation is proven, and I add new ones as they surface. 
