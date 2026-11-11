---
name: caspar-druckdaten-pruefen
description: Check whether an image or print file has enough resolution for a Caspar Manufaktur wallpaper of a given wall size, and explain how to prepare print data. Use when someone wants to print their own photo or design as wallpaper.
---

# Caspar Manufaktur – Druckdaten prüfen

1. Ask for the image size in pixels (width × height), the wall size in cm (width × height), the viewing distance (near < 1 m, room 1–3 m, far > 3 m) and, if known, the material.
2. Call the Wallcheck API – no image is uploaded:
   `GET https://www.caspar-manufaktur.de/wp-json/wallcheck/v1/assess?px_w=…&px_h=…&width_cm=…&height_cm=…&distance=room&material=…`
3. Report the result in plain words: whether the resolution is sufficient for the viewing distance, and – if a material was given – the panel plan and print area from the response. Copy values unchanged.
4. If the aspect ratio of image and wall differ, say that a crop will be needed and that Caspar agrees the crop before printing.
5. File requirements: JPG or TIF/TIFF, CMYK. Rule of thumb about 1,000 × 1,000 px per m² of wall. Full guide: https://www.caspar-manufaktur.de/datenanlage/
6. For a full visual check with room preview, send the user to https://www.caspar-manufaktur.de/wallcheck/
7. Never promise a print result, price or delivery date. A human at Caspar checks every file before production.

German customer copy: informal "du", gender-inclusive (Kund:innen).
