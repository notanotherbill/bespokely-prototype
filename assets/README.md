# Bespoke-ly — Media assets

Drop your real files into this folder using the **exact filenames** below. The
prototype already references these paths, so each file appears 1:1 with no markup
changes. Until a file is present, the beat shows a tasteful on-brand gradient
placeholder (with the label), so nothing ever looks broken.

## Photography — ~4:5 portrait, JPG or WebP, ~2× (≈900×1125px)

| File | Beat | Subject |
|------|------|---------|
| `hero-bespoke.jpg` | Hero | A bespoke gift — "designed & made" floating card |
| `hero-unboxing.jpg` | Hero | A pristine unboxing moment — floating card |
| `hero-onbrand.jpg` | Hero | On-brand detailing — floating card |
| `beat01-unforgettable.jpg` | 01 — Stakes | The "unforgettable" hero gift — the version people screenshot |
| `beat01-keepsake.jpg` | 01 — Stakes | A bespoke keepsake — kept on the desk for years |
| `beat01-reveal.webp` | 01 — Stakes | "First impression" — says everything before you do (filename kept from earlier reveal art) |
| `beat02-creative.jpg` | 02 — Guide | Creative / concepting — studio, sketches, ideation |
| `beat02-product.jpg` | 02 — Guide | Production / making — real products in the UK/NL studio |
| `beat02-fulfilment.jpg` | 02 — Guide | Fulfilment — hand-packing, pristine dispatch |
| `beat04-event-gifts.jpg` | 04 — Transformation | Event gifts — launches / summits / on-stage |
| `beat04-merchandise.jpg` | 04 — Transformation | Branded merchandise — apparel / drinkware / desk |
| `beat04-vip-gifting.jpg` | 04 — Transformation | VIP gifting — high-touch, individual |

> **Hero & beat-02/04 cards reveal more on hover** (a `chip-detail` line + lift/tilt),
> so favour images that still read well slightly zoomed.

### "Explore our work" marquee — ~4:3 landscape (≈1200×900px)

The autoplaying strip above the footer. Each is a large project-type thumbnail; missing files
show the same on-brand placeholder. Add/remove cards by editing the `.marquee-row` in the markup.

| File | Project type |
|------|--------------|
| `work-event-gifts.jpg` | Event gifts |
| `work-merchandise.jpg` | Merchandise |
| `work-vip-gifting.jpg` | VIP gifting |
| `work-drinkware.jpg` | Drinkware |
| `work-apparel.jpg` | Apparel |
| `work-keepsakes.jpg` | Keepsakes |
| `work-stationery.jpg` | Stationery |
| `work-tech.jpg` | Tech gifts |

## Client logos — cleared marks, mono SVG preferred (PNG w/ transparency fine)

Rendered in a unified single tone on a paper card. The first four are wired with the
real client names; `logo-client5…8` are **placeholders** (currently labelled
SPOTIFY / GOOGLE / STRIPE / AIRBNB in the markup) — replace both the file and the
`<span class="wordmark">` text with the real cleared clients.

| File | Client |
|------|--------|
| `logo-netflix.svg` | Netflix |
| `logo-hsbc.svg` | HSBC |
| `logo-nike.svg` | Nike |
| `logo-openai.svg` | OpenAI |
| `logo-client5.svg` | _placeholder_ |
| `logo-client6.svg` | _placeholder_ |
| `logo-client7.svg` | _placeholder_ |
| `logo-client8.svg` | _placeholder_ |

> Swap `.svg` → `.png` in the `<img>` tags inside the Proof beat if you only
> have raster logos. Everything else stays the same.

## Copy / numbers still to confirm (not assets, but needed for sign-off)

- **Proof stats** are placeholders: `12 yrs` and `94%` repeat rate — set the real
  figures via `data-count` / `data-suffix` on the `.stat .n` spans in the Proof beat.
- **Beat-01 pills** (`Generic / Forgettable / Last-minute`) are live for testing the
  decay animation — reword in the markup if needed.
