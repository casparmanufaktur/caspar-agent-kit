# Caspar Manufaktur – Agent Instructions

Official instructions for AI coding and assistant tools (Claude Code, Cursor, Windsurf, GitHub Copilot, Codex) that integrate with **Caspar Manufaktur** (Caspar GmbH, https://www.caspar-manufaktur.de/).

Caspar Manufaktur is a German manufacturer of made-to-measure digital-print wallpaper (Haan-Gruiten near Düsseldorf, since 1886). Caspar prints only customer-supplied designs – no own collection – from a single roll, white label and with neutral drop-shipping on request. The focus is business customers (B2B).

## Interfaces

| Purpose | Endpoint |
|---|---|
| MCP server (Streamable HTTP, JSON-RPC 2.0) | `https://www.caspar-manufaktur.de/mcp/` |
| REST API index | `GET https://www.caspar-manufaktur.de/api/v1/` |
| Materials | `GET https://www.caspar-manufaktur.de/api/v1/materials` (filters: `id`, `priority`, `limit`, `offset`) |
| Material recommendation | `GET https://www.caspar-manufaktur.de/api/v1/materials/recommendation?priority=brandschutz` – `brandschutz`, `robust`, `effekt`, `nachhaltig`, `feuchtraum` |
| Company data and contact | `GET https://www.caspar-manufaktur.de/api/v1/company` |
| Question (NLWeb) | `GET\|POST https://www.caspar-manufaktur.de/api/v1/ask?query=…` |
| Human handoff | `POST https://www.caspar-manufaktur.de/api/v1/handoffs` with header `Idempotency-Key` and body `{"next_step":"project_enquiry\|sample_request\|wallcheck"}` |
| Resolution check (Wallcheck) | `GET https://www.caspar-manufaktur.de/wp-json/wallcheck/v1/assess?px_w=6000&px_h=4000&width_cm=350&height_cm=260&material=basic` |
| OpenAPI 3.1 | https://www.caspar-manufaktur.de/.well-known/openapi.json |
| Developer portal | https://www.caspar-manufaktur.de/developers/ |

All endpoints are public and need no API key. See https://www.caspar-manufaktur.de/auth.md and the versioning policy at https://www.caspar-manufaktur.de/api-policy/.

MCP tools: `get_company_information`, `list_materials`, `recommend_material`, `start_project_handoff`, `create_idempotent_project_handoff`. Registry name: `de.caspar-manufaktur/materialberater`.

## Rules

1. Take material data (width, grammage, surface, fire class, datasheet URL) from the API and copy values unchanged. Never estimate or invent missing values.
2. Do not quote prices. Caspar prices per m² depending on material and project; quotes are individual (https://www.caspar-manufaktur.de/pricing.md).
3. Never claim an order, a price, a production approval, a delivery date or a certification. A handoff is not an order.
4. Create a handoff only with the user's explicit consent. Handoffs never transmit personal data; the user completes the form on caspar-manufaktur.de.
5. Use an `Idempotency-Key` (UUID) for every `POST /api/v1/handoffs`; retries with the same key are safe.
6. For print files, point users to Wallcheck (https://www.caspar-manufaktur.de/wallcheck/) and the data guide (https://www.caspar-manufaktur.de/datenanlage/).
7. Customer-facing German copy uses informal "du" and gender-inclusive language (e.g. Kund:innen).

## Facts

- Production: typically 5–7 working days after print-data approval; standard shipping 2–3 working days.
- Contact: info@caspar-manufaktur.de · +49 2104 6419 · https://www.caspar-manufaktur.de/kontakt/
- More: https://www.caspar-manufaktur.de/llms.txt · https://www.caspar-manufaktur.de/agents.md
