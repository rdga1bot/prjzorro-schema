# prjzorro-schema

OpenAPI 3.1 REST API schema for **Prozorro Analytics** — an open-source platform for analyzing Ukrainian public procurement data from [Prozorro](https://prozorro.gov.ua) (CC BY).

## Coverage

42 endpoints across 9 tag groups:

| Tag | Endpoints |
|---|---|
| Tenders | list, detail, similar, spending, benchmark, related, PDF report |
| Companies | profile, tenders, network graph, PDF report |
| Stats | dashboard, CPV breakdown, trend, top suppliers, risk leaders |
| Search | full-text search, autocomplete |
| Export | CSV / XLSX download |
| Auth | register, login, refresh, logout, profile, API keys, org branding |
| Orgs | create, list, members, invite, accept invite, remove member |
| Alerts | create, list, delete (email subscriptions) |
| Webhooks | create, list, delete, deliveries, test |

## Usage

### Swagger UI (local preview)

```bash
npx @redocly/cli preview-docs openapi.yaml
```

### Generate a client SDK

```bash
# Python
openapi-generator-cli generate -i openapi.yaml -g python -o ./client-py

# TypeScript (fetch)
openapi-generator-cli generate -i openapi.yaml -g typescript-fetch -o ./client-ts
```

### Validate

```bash
npx @redocly/cli lint openapi.yaml
```

## Authentication

- **Bearer JWT** — obtained via `POST /api/v1/auth/login`
- **API Key** — `X-API-Key` header, created via `POST /api/v1/auth/keys`

## License

GNU General Public License v3.0 — see [LICENSE](LICENSE).

Data: Prozorro Public API, [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
