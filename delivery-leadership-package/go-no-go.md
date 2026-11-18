# Go / No-Go: Launch Decision

> Copy to `delivery-leadership-package/go-no-go.md`. This is the call for Friday's launch demo. Make it **from** the CI result, not in spite of it.

**Date / time:** 11/18/26 
**Decision:** ☐ GO   ☐ NO-GO   X GO WITH CONDITIONS

## CI evidence

- Latest run on `delivery/lead` (both jobs): _green / red_  ·  link: _(https://github.com/asc1-student06/evergreen-quote-launch/actions)
- Workflow file: `.github/workflows/ci.yml`
- What the workflow actually checked: both jobs API tests and client type-check/build

## What "GO" would mean

- Merge `delivery/lead` → `main`, squash, delete branch.
- Tag the merge commit `launch`.

## What "NO-GO" would mean

- Hold the merge until: both CI jobs are green on my branch, my kind cluster shows 3 API pods + mongo running, and the app saves a quote that survives a reload. 
- Owner of that condition: Kristen Marturano (delivery lead) for my stack and the merge. The platform team owns the shared demo cluster incident, which doesn't gate this call.
- Re-evaluate at: Thurs 10, at check-in.

## My call

GO WITH CONDITIONS for Friday's launch demo. Friday's demo runs on my stack (the local kind cluster plus the wired client), and both pieces of evidence for it are green. The shared-environment incident is real and tracked, but the platform team owns it, and nothing in my demo or merge path depends on that cluster.

Conditions: 
1) my CI stays green on the PR
2) my kind cluster is still healthy at Thursdays rehearsal
3) the shared incident stays out of my merge path. I won't adopt the renamed variable or any change from that cluster.

What whould change my mind:
 my own CI or cluster goes red; the incident turns out to involve a change that's also in my branch; or the sponsor decides the demo must run on the shared environment. 


Message updates:

To Platform team owner:

Hi Platform team. Since about 13:25, the shared demo cluster's three API pods are in CrashLoopBackOff, and their logs show the app can't connect to its database. The mongo pod itself is healthy (Running, 0 restarts). The restarts line up with this afternoon's environment-variable tidy-up. The deployment now shows MONGO_URI, while the app reads MONGODB_URI. Can your team confirm whether the rename is the cause, and own restoring the name the app expects? What time should we expect it back? I'm not making any changes to that environment. My own cluster and CI are green, so take the time you need to get it right, and I'll keep the managers updated.

To the manager who reported it:

Thanks for flagging this. The "Could not load recent quotes" message is coming from the shared demo environment, which had a configuration change this afternoon. The platform team owns it and is looking into it now. Friday's launch demo doesn't run on that environment. It runs on our verified setup, which is healthy, and our automated checks are all passing. I'll update you by 4pm today with the platforms teams status, and sooner if anything changes.




