# Cryptomus

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Cryptomus is a cryptocurrency payment gateway and ecosystem providing REST APIs for merchants and developers to accept crypto payments, create invoices, process payouts, manage recurring subscriptions, and access real-time exchange rate and market data across 100+ cryptocurrencies.

## APIs

| API | Description | Base URL |
|-----|-------------|----------|
| Merchant Payment API | Accept crypto payments, create invoices, manage static wallets | `https://api.cryptomus.com/v1` |
| Payout API | Process withdrawals, mass payouts, wallet transfers | `https://api.cryptomus.com/v1` |
| Recurring Payments API | Subscription billing with weekly/monthly/quarterly periods | `https://api.cryptomus.com/v1` |
| Exchange and Market Data API | Real-time rates, order books, trading, WebSocket streams | `https://api.cryptomus.com/v2` |

## Authentication

All Merchant API requests require two HTTP headers:

- `merchant` — your merchant UUID from account settings
- `sign` — MD5 hash of `base64_encode(request_body) + API_KEY`

Separate API keys are required for payment and payout operations.

## Key Endpoints

- `POST /v1/payment` — Create a payment invoice
- `POST /v1/payout` — Create a payout
- `POST /v1/recurrence/create` — Create a recurring payment plan
- `POST /v1/payment/services` — List available payment services
- `POST /v1/balance` — Get merchant and user wallet balances
- `POST /v1/transfer/to-business` — Transfer funds to business wallet
- `POST /v2/user-api/convert/calculate` — Calculate exchange conversion
- `WSS wss://api-ws.cryptomus.com/ws` — Real-time market data WebSocket

## Fees

- Payment processing: 2% standard, negotiable to 0.4% by volume
- Trading: from 0.04% (maker/taker tiered model)
- Auto-convert: Free
- Internal transfers: Free

## Resources

- Documentation: https://doc.cryptomus.com/
- Fee Schedule: https://cryptomus.com/fees/payment
- Website: https://cryptomus.com/
