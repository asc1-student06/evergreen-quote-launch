# Decision Memo: _short title here_

> Copy to `delivery-leadership-package/decision-memo.md`. Target length: ~250 words. Write for a non-technical reader. Name the options you **rejected**, not just the one you picked.

**Date:** 11/17/26
**Author:** Kristen Marturano
**Decision area:** Keep the instant estimate in the browser, with the server as the price of record

## Context

Once we connected the website to the quote service, the same quote showed two prices: $425 as an estimate and $450 once saved. Nothing was broken. The website and the service each calculate the price, and their rate tables had fallen out of sync. The sponsor ruled that the server is the source of truth, and I aligned the websites rates. But the price is still calculated in two places, so this could happen again.

## Options considered

1. **Option A: Keep Both ** The browser shows an instant estimate while the customer types, and the server decides the official price when they save. It's fast for the customer, but thw two rate tables must be kept in sync.
2. **Option B: Server only ** Every estimate is a request to the server. That gives one price everywhere but it adds a delay on every keystroke, and estimate stops working if the service is down. 

## Recommendation

Option 1 for this launch. Plan to remove the duplication after launch.

## Why

- the rates match today, and swapping how estimates work two days before launch adds risk for no customer benefit.
- the customer keeps an instant, respoonsive estimate.
- the saved price, the one thst matters, always comes from the server.
- after launch the website should read its rates from the server, so there is only one table to update.

## What would change my mind

If an estiamte and a saved price disagree again before Friday, I'd treat the duplication as a launch risk, not a post-launch cleanup, and raise it with the sponsor. 