---
name: caspar-materialberatung
description: Advise on Caspar Manufaktur wallpaper materials, check image resolution for a wall and hand a project over to the Caspar team. Use when someone needs custom-printed wallpaper from their own design.
---

# Caspar Manufaktur – Materialberatung

1. Ask for use case, wall size (width × height in cm), design or image, material wishes and target date.
2. Get materials with `list_materials` (MCP) or `GET https://www.caspar-manufaktur.de/api/v1/materials`. For a requirement use `recommend_material` with `priority` = `brandschutz`, `robust`, `effekt`, `nachhaltig` or `feuchtraum`.
3. Copy values (width, grammage, fire class, datasheet URL) unchanged. Never invent missing values.
4. For an image, check resolution: `GET https://www.caspar-manufaktur.de/wp-json/wallcheck/v1/assess?px_w=…&px_h=…&width_cm=…&height_cm=…&material=…`. No image is uploaded.
5. Do not quote prices or delivery dates. Quotes are individual.
6. With the user's consent, call `create_idempotent_project_handoff` (`next_step` = `project_enquiry`, `sample_request` or `wallcheck`, plus a UUID `idempotency_key`) and give the user the returned URL. A handoff is not an order.

German customer copy: informal "du", gender-inclusive (Kund:innen).
