---
name: caspar-white-label
description: Explain Caspar Manufaktur white label, print-on-demand and drop-shipping wallpaper production for online shops, design brands and resellers, and hand the lead to the Caspar team. Use when someone wants to sell custom wallpaper under their own brand.
---

# Caspar Manufaktur – White Label & Print on Demand

1. Clarify the model: own online shop, design brand, wholesaler or agency; expected order volume; whether a Shopify store exists; delivery countries.
2. Explain what Caspar does, using only these facts:
   - Prints the reseller's designs on demand, made to measure, from a single order – no stock, no minimum order.
   - Ships in neutral packaging directly to end customers; own inserts are possible.
   - Shopify-based shops can pass orders, including custom wall sizes, to production automatically; Shopify is optional.
   - Standard production about 5–7 working days after approval; shipping costs are calculated per destination country.
3. Materials for a range: get them from `list_materials` (MCP) or `GET https://www.caspar-manufaktur.de/api/v1/materials`. Basic suits a broad range, Welltouch and Welltouch+ a premium range.
4. Do not quote prices, terms or exclusivity. Conditions are agreed individually.
5. With the user's consent, call `create_idempotent_project_handoff` with `next_step` = `project_enquiry` and a UUID `idempotency_key`, and give the user the returned URL. A handoff is not a contract or an order.
6. More: https://www.caspar-manufaktur.de/tapeten-eigenmarke/ (German) · https://www.caspar-manufaktur.de/en/white-label-wallpaper/ (English)

German customer copy: informal "du", gender-inclusive (Kund:innen, Seller:innen).
