# Guusto (guusto)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Guusto is an employee recognition and rewards platform that lets teams send digital gifts, run peer-to-peer and top-down recognition programs, and redeem rewards across a large merchant network, prepaid Mastercard, and charitable donations. Guusto exposes a documented REST **Gifts API** for programmatically ordering gifts, tracking order status, retrieving workspace and member reward budgets, and pulling recognition activity and manager-insight reports.

**API access is gated to the Guusto Premium plan.** The Free, Lite, and Essential tiers do not include API access. The API is real and OpenAPI-backed (docs.guusto.com), authenticated with a Bearer API token plus an `X-Workspace-id` header, and offers a production environment (`https://api.guusto.com/api/v1`) and a demo/test environment (`https://api-demo.guusto.io/api/v1`). Guusto's own API is request/response REST only - there is **no** documented public WebSocket/streaming API. The endpoints documented here are confirmed from Guusto's published API reference (not modeled).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/guusto/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/guusto/refs/heads/main/apis.yml)

## Tags

- Employee Recognition
- Rewards
- Gifting
- Gift Cards
- HR
- Rewards and Recognition

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Guusto Gifts API

Order one or more digital gifts to recipients (by email or employee number), then track each order's processing status and details. Submit a batch of up to 20 gift items in a single order with a message, amount, currency, and optional language.

- **Human URL:** [https://docs.guusto.com/version/openapi/order-gift](https://docs.guusto.com/version/openapi/order-gift)
- **Base URL:** `https://api.guusto.com/api/v1`

Endpoints:

- `POST /api/v1/orders`
- `GET /api/v1/orders/status/{requestId}`
- `GET /api/v1/orders/{requestId}`

#### Tags

- Gifts
- Orders
- Recognition

#### Properties

- [Documentation](https://docs.guusto.com/)
- [API Reference](https://docs.guusto.com/version/openapi/order-gift)
- [OpenAPI](openapi/guusto-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/guusto.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/guusto.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Guusto Account Budget API

Retrieve available reward budget balances for a workspace, for a single member by employee number, or for all members - scoped by currency (CAD or USD) - so integrations can check spending power before ordering gifts.

- **Human URL:** [https://docs.guusto.com/version/openapi/account-budget](https://docs.guusto.com/version/openapi/account-budget)
- **Base URL:** `https://api.guusto.com/api/v1`

Endpoints:

- `GET /api/v1/balances/workspaces/currencies/{currency}`
- `GET /api/v1/balances/members/{employeeNumber}/currencies/{currency}`
- `GET /api/v1/balances/members/currencies/{currency}`

#### Tags

- Budget
- Balances
- Rewards

#### Properties

- [Documentation](https://docs.guusto.com/)
- [API Reference](https://docs.guusto.com/version/openapi/account-budget)
- [OpenAPI](openapi/guusto-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/guusto.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/guusto.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Guusto Reports API

Pull paginated recognition activity for teams (sender, receiver, status, reason, timestamps) and manager-insight data on when team members were last recognized by their managers. The manager-insight resource is rate limited.

- **Human URL:** [https://docs.guusto.com/version/openapi/reports](https://docs.guusto.com/version/openapi/reports)
- **Base URL:** `https://api.guusto.com/api/v1`

Endpoints:

- `GET /api/v1/reports/teams/activity`
- `GET /api/v1/reports/members/last-recognized` (rate limited)

#### Tags

- Reports
- Analytics
- Manager Insights

#### Properties

- [Documentation](https://docs.guusto.com/)
- [API Reference](https://docs.guusto.com/version/openapi/reports)
- [OpenAPI](openapi/guusto-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/guusto.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/guusto.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Authentication

- **Scheme:** Bearer API token (issued from the Guusto workspace on the Premium plan)
- **Required header:** `X-Workspace-id` (scopes the request to a workspace)
- **Optional header:** `X-Customer-Request-Id` (caller-supplied correlation / idempotency id)

## Environments

- **Production:** `https://api.guusto.com/api/v1`
- **Demo / Test:** `https://api-demo.guusto.io/api/v1`

## Rate Limits

Guusto does not publish blanket numeric rate limits. The Manager Insights report (`GET /api/v1/reports/members/last-recognized`) is documented as rate limited and returns an error indicating the limit has been reached when exceeded. See [rate-limits/guusto-rate-limits.yml](rate-limits/guusto-rate-limits.yml).

## Plans and Pricing

Per-seat SaaS subscription across four tiers (USD or CAD, monthly or yearly). API access is included only on Premium.

- **Free** — $0; send rewards, mobile app, 100+ merchants; no API.
- **Lite** — $150/month; 1 sender + 250 recipient seats; no API.
- **Essential** — $4.00/sender seat + $0.70/recipient seat per month; $200/month minimum; no API.
- **Premium** — $5.00/sender seat + $1.00/recipient seat per month; $500/month minimum; **API access included**.

Gift face value is funded separately from the subscription. See [plans/guusto-plans-pricing.yml](plans/guusto-plans-pricing.yml) and [finops/guusto-finops.yml](finops/guusto-finops.yml).

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/guusto)
- [Website](https://guusto.com)
- [Documentation](https://docs.guusto.com/)
- [Plans](plans/guusto-plans-pricing.yml)
- [Rate Limits](rate-limits/guusto-rate-limits.yml)
- [Fin Ops](finops/guusto-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
