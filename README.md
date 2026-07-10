# Guusto (guusto)

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
