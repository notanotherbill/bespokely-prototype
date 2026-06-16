# Artwork brief — the animated "B" ribbon

**For:** the graphic designer
**From:** web build team
**Purpose:** supply the logo in a form the website can *animate being drawn on*, and that *weaves correctly* where the ribbon crosses itself.

---

## 1. What we're building (30-second version)

On the homepage, the Bespoke-ly **B** is drawn on, stroke by stroke, as the visitor scrolls — as if a pen is drawing the ribbon in real time. Where the ribbon crosses over itself, it should read like a **woven ribbon**: one strand clearly *over*, one *under*.

To do that the code needs to know two things the flat logo can't tell it:
1. **The path the "pen" travels** (the centre-line of the ribbon, start to finish).
2. **Which strand is on top at the crossing** (the over/under).

---

## 2. Why the current file doesn't work

All we currently have is the **final, flattened logo** — one solid filled shape. From that, the code had to *guess*:

- It **auto-traced a centre-line** from the solid shape. That trace **starts at a corner of the ribbon's tip** instead of the centre of the ribbon's end — so the draw begins from a corner, not cleanly from the end of the ribbon.
- The solid shape **merges the two strands into one** at the crossing. There's no "over" and "under" any more, so the weave can't be rendered — one strand smears in early and it looks broken.

Neither can be fixed in code, because the information was lost when the artwork was flattened. **We need the artwork in its "drawable" form.** Everything below is about getting that.

---

## 3. What we need (the deliverable)

### ✅ Best option — the ribbon as *open stroked paths*, before "Expand / Outline Stroke"

The B was almost certainly drawn as a stroked line and then expanded into the filled shape we have. We want it **before** that expand step:

- The ribbon as **open path(s) with a stroke weight** (not a filled outline).
- **Split into the two strands at the crossing**, stacked so one is clearly **on top**.
- Drawn/numbered in the order the ribbon is "written" (start → finish).

From those two stroked paths the code gets *everything*: the pen path (the line itself), the ribbon width (the stroke weight), the weave (one strand layered over the other), and clean ends (the stroke caps).

### ◻︎ If the pre-expand paths are gone — rebuild it as two things

1. **The spine** — one **open path** running down the *exact centre* of the ribbon, from the **dead centre of the starting tip** to the **dead centre of the ending tip**. One continuous line, no fill.
2. **The ribbon, split into 2 overlapping filled pieces** at the crossing — the *under* strand and the *over* strand — stacked in the correct order.

Either route solves **both** problems at once.

---

## 4. Specs / checklist

Please make sure the delivered file ticks all of these:

- **Format:** SVG, **plus** the editable source (`.ai` or `.fig`).
- **Same canvas as the current logo** so it lines up exactly — artboard / viewBox **`0 0 4235 5355`** (the current logo's coordinate space). Don't resize or recentre.
- **Separate, named layers/paths** — e.g. `spine`, `strand-under`, `strand-over` (or `stroke-1`, `stroke-2`). Not one merged path.
- **No clipping masks**, and **no transforms left un-flattened** (apply / flatten any scaling or rotation so the path coordinates are the real ones).
- **Open paths stay open** (don't auto-close them). Fills off on the spine.
- **Note the stroke width** of the ribbon (in the same units, ~430 at its widest today) and whether it's **constant** or tapers.
- **Note the end-cap style** you intend for the two tips (flat / round) — this is literally how the drawn ribbon starts and ends.
- **Tell us which strand is "over"** at the crossing, and **the draw order** (which strand the pen draws first).

---

## 5. The two specific trouble spots (for reference)

In the current logo's coordinate space (`0 0 4235 5355`):

- **The start tip** is near **(1405, 291)** — today the trace starts at the bottom *corner* here; we need the spine to start at the **centre of that end edge**.
- **The self-crossing** is near **(1686, 4323)** — the two strands pass through the same point twice; this is where we need them as separate, stacked pieces.

(If the B has more than one self-crossing once you look closely, split at **each** one the same way.)

---

## 6. How we'll check it's right (acceptance)

1. **Stroking the spine** at the stated width **reproduces the ribbon exactly** (no drift from the real outline).
2. The spine **starts at the centre of the start edge** and **ends at the centre of the end edge** — so the draw-on begins and finishes cleanly on the ribbon's ends.
3. At the crossing, the two strands **overlap with one unambiguously on top** — hide the top strand and the bottom one is still a complete, continuous ribbon underneath.

If those three hold, the draw-on and the weave both "just work" — no more compromises in code.

---

*Once this lands, drop the files into `assets/` and ping the build team; wiring it up is a small change on our side (no new design needed).*
