# PedBurn — Pediatric Burn TBSA & Fluid Resuscitation Calculator

**Research prototype — not a medical device. All outputs must be verified by the treating clinician. Not for clinical use.**

PedBurn is a single-file web application for estimating the percentage of Total Body Surface Area (TBSA) burned in pediatric patients and converting it into a fluid resuscitation plan.

## Why

Children's body proportions change with age — an infant's head is ~20% of body surface, an adolescent's ~9% — so adult tools like the Rule of Nines systematically mis-estimate pediatric burns, and visual estimation varies between clinicians. Small TBSA errors become large fluid-prescription errors.

## Features

- **Age-adjusted Lund–Browder body map** — tappable front/back child figure; region weights follow the patient's age automatically (0 / 1 / 5 / 10-year chart columns)
- **Draw exact area mode** — trace the actual burned patch with a finger; the app measures pixel-accurately how much of each region is covered (no quarter-step rounding)
- **Pediatric modified Parkland engine** — 3 mL/kg/%TBSA over 24 h (classic 4 mL selectable), half in the first 8 h *from the time of burn*, with correct handling of delayed presentation and fluids already given
- **Mandatory maintenance fluids** — Holliday–Segar 4-2-1 rule added automatically for children
- **Safety rails** — >10% TBSA IV-resuscitation threshold warning, urine-output titration target (≈1 mL/kg/h), partial/full-thickness-only reminder, permanent disclaimer
- **Built-in self-test** — one tap re-derives 16 hand-calculated values and shows PASS/FAIL, so correctness can be verified at the bedside
- **Clinical photo attachment** — camera capture, stored on-device only; will host AI burn segmentation in a future phase
- **Print summary** for the patient chart

## Use

Open `index.html` in any modern browser — no installation, no build step, no internet needed. Works on phones and tablets.

Demo presets for training/documentation: append `#demo=ex1` … `#demo=ex4` or `#demo=selftest` to the URL.

## Roadmap

| Phase | Deliverable | Status |
|---|---|---|
| 1 | Age-adjusted Lund–Browder + modified Parkland engine | Done |
| 2 | Interactive body map app (tap + draw modes) | Done |
| 3 | AI burn segmentation from photos (U-Net) pre-filling the body map | In development |
| 4 | Hospital dataset protocol (ethics, de-identification, annotation) | In preparation |
| 5 | Clinical validation study vs. clinician estimates | Planned |

## Disclaimer

This software is provided for research and demonstration purposes only. It is not a registered medical device and must not be used to direct patient care. Clinical sample images used in local testing are excluded from this repository for copyright reasons.
