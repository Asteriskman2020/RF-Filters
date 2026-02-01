# All HF Ham Band Low Pass Filters — 5W QRP

## Common Design Parameters
- **Topology**: 5-element Chebyshev 0.5dB ripple
- **Impedance**: 50 ohm
- **Power**: 5W (V_peak = 22.4V, use 50V+ rated caps)
- **Caps**: C0G/NP0 ceramic only
- **Wire**: 24 AWG enameled for 160m/80m/40m, 26 AWG for 30m and up
- **Cores**: T50-2 (red) for 160m/80m, T50-6 (yellow) for 40m–6m

## Schematic (all bands)

```
IN o───┬───[L1]───┬───[L2]───┬───o OUT
       │          │          │
      C1         C2         C3
       │          │          │
      GND        GND        GND
```

---

## 160m Band (1.8–2.0 MHz) — Cutoff 2.5 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 2172 pF | **2200 pF** | — |
| L1 | 3914 nH | **3.9 uH** | 28t on T50-2 (red) |
| C2 | 3235 pF | **3300 pF** | — |
| L2 | 3914 nH | **3.9 uH** | 28t on T50-2 (red) |
| C3 | 2172 pF | **2200 pF** | — |

- T50-2: AL = 4.9 nH/t^2, L = 28^2 x 4.9 = 3841 nH (spread turns for 3.9 uH)
- 2nd harmonic (4 MHz): ~-35 dB | 3rd (6 MHz): ~-55 dB

---

## 80m Band (3.5–4.0 MHz) — Cutoff 5.0 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 1086 pF | **1000 pF + 100 pF** | — |
| L1 | 1957 nH | **2.0 uH** | 20t on T50-2 (red) |
| C2 | 1617 pF | **1500 pF + 120 pF** | — |
| L2 | 1957 nH | **2.0 uH** | 20t on T50-2 (red) |
| C3 | 1086 pF | **1000 pF + 100 pF** | — |

- T50-2: AL = 4.9 nH/t^2, L = 20^2 x 4.9 = 1960 nH
- 2nd harmonic (8 MHz): ~-35 dB | 3rd (12 MHz): ~-55 dB

---

## 40m Band (7.0–7.3 MHz) — Cutoff 8.5 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 639 pF | **680 pF** | — |
| L1 | 1151 nH | **1.15 uH** | 17t on T50-6 (yellow) |
| C2 | 952 pF | **1000 pF** | — |
| L2 | 1151 nH | **1.15 uH** | 17t on T50-6 (yellow) |
| C3 | 639 pF | **680 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 17^2 x 4.0 = 1156 nH
- 2nd harmonic (14.6 MHz): ~-35 dB | 3rd (21.9 MHz): ~-55 dB

---

## 30m Band (10.1–10.15 MHz) — Cutoff 12 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 453 pF | **470 pF** | — |
| L1 | 815 nH | **810 nH** | 14t on T50-6 (yellow) |
| C2 | 674 pF | **680 pF** | — |
| L2 | 815 nH | **810 nH** | 14t on T50-6 (yellow) |
| C3 | 453 pF | **470 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 14^2 x 4.0 = 784 nH (spread turns for 810 nH)
- 2nd harmonic (20.3 MHz): ~-35 dB | 3rd (30.45 MHz): ~-55 dB

---

## 20m Band (14.0–14.35 MHz) — Cutoff 16 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 339 pF | **330 pF** | — |
| L1 | 612 nH | **610 nH** | 12t on T50-6 (yellow) |
| C2 | 506 pF | **470 pF + 33 pF** | — |
| L2 | 612 nH | **610 nH** | 12t on T50-6 (yellow) |
| C3 | 339 pF | **330 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 12^2 x 4.0 = 576 nH (spread turns for 610 nH)
- 2nd harmonic (28 MHz): ~-35 dB | 3rd (42 MHz): ~-55 dB

---

## 17m Band (18.068–18.168 MHz) — Cutoff 21 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 259 pF | **270 pF** | — |
| L1 | 466 nH | **480 nH** | 11t on T50-6 (yellow) |
| C2 | 385 pF | **390 pF** | — |
| L2 | 466 nH | **480 nH** | 11t on T50-6 (yellow) |
| C3 | 259 pF | **270 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 11^2 x 4.0 = 484 nH (compress slightly for 480 nH)
- 2nd harmonic (36.3 MHz): ~-35 dB | 3rd (54.5 MHz): ~-55 dB

---

## 15m Band (21.0–21.45 MHz) — Cutoff 25 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 217 pF | **220 pF** | — |
| L1 | 391 nH | **400 nH** | 10t on T50-6 (yellow) |
| C2 | 323 pF | **330 pF** | — |
| L2 | 391 nH | **400 nH** | 10t on T50-6 (yellow) |
| C3 | 217 pF | **220 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 10^2 x 4.0 = 400 nH
- 2nd harmonic (42.9 MHz): ~-35 dB | 3rd (64.4 MHz): ~-55 dB

---

## 12m Band (24.89–24.99 MHz) — Cutoff 29 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 187 pF | **180 pF** | — |
| L1 | 337 nH | **324 nH** | 9t on T50-6 (yellow) |
| C2 | 279 pF | **270 pF** | — |
| L2 | 337 nH | **324 nH** | 9t on T50-6 (yellow) |
| C3 | 187 pF | **180 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 9^2 x 4.0 = 324 nH (spread turns for 337 nH)
- 2nd harmonic (49.98 MHz): ~-35 dB | 3rd (74.97 MHz): ~-55 dB

---

## 10m Band (28.0–29.7 MHz) — Cutoff 34 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 160 pF | **150 pF** | — |
| L1 | 288 nH | **290 nH** | 9t on T50-6 (yellow) |
| C2 | 238 pF | **220 pF + 18 pF** | — |
| L2 | 288 nH | **290 nH** | 9t on T50-6 (yellow) |
| C3 | 160 pF | **150 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 9^2 x 4.0 = 324 nH (compress turns for 290 nH)
- 2nd harmonic (59.4 MHz): ~-35 dB | 3rd (89.1 MHz): ~-55 dB

---

## 6m Band (50.0–54.0 MHz) — Cutoff 60 MHz

| Part | Value | Practical | Toroid |
|------|-------|-----------|--------|
| C1 | 91 pF | **91 pF** | — |
| L1 | 163 nH | **144 nH** | 6t on T50-6 (yellow) |
| C2 | 135 pF | **130 pF** | — |
| L2 | 163 nH | **144 nH** | 6t on T50-6 (yellow) |
| C3 | 91 pF | **91 pF** | — |

- T50-6: AL = 4.0 nH/t^2, L = 6^2 x 4.0 = 144 nH (spread turns for 163 nH)
- 2nd harmonic (108 MHz): ~-35 dB | 3rd (162 MHz): ~-55 dB
- **VHF note**: keep all leads under 3 mm, use ground plane PCB

---

## Quick Reference Table

| Band | Cutoff | C1/C3 | C2 | L1/L2 | Core | Turns |
|------|--------|-------|----|-------|------|-------|
| 160m | 2.5 MHz | 2200 pF | 3300 pF | 3.9 uH | T50-2 (red) | 28t |
| 80m | 5.0 MHz | 1100 pF | 1620 pF | 2.0 uH | T50-2 (red) | 20t |
| 40m | 8.5 MHz | 680 pF | 1000 pF | 1.15 uH | T50-6 (yellow) | 17t |
| 30m | 12 MHz | 470 pF | 680 pF | 810 nH | T50-6 (yellow) | 14t |
| 20m | 16 MHz | 330 pF | 503 pF | 610 nH | T50-6 (yellow) | 12t |
| 17m | 21 MHz | 270 pF | 390 pF | 480 nH | T50-6 (yellow) | 11t |
| 15m | 25 MHz | 220 pF | 330 pF | 400 nH | T50-6 (yellow) | 10t |
| 12m | 29 MHz | 180 pF | 270 pF | 324 nH | T50-6 (yellow) | 9t |
| 10m | 34 MHz | 150 pF | 238 pF | 290 nH | T50-6 (yellow) | 9t |
| 6m | 60 MHz | 91 pF | 130 pF | 144 nH | T50-6 (yellow) | 6t |

## Build Notes (5W)
- All toroids use **T50** size for better current handling at 5W
- T50-2 (red): AL = 4.9 nH/t^2 — best for 160m/80m (higher permeability)
- T50-6 (yellow): AL = 4.0 nH/t^2 — best for 40m–6m (lower loss at HF/VHF)
- Use **24 AWG** wire for 160m/80m (higher current), **26 AWG** for 30m and up
- All capacitors: **C0G/NP0** ceramic, 50V minimum rating
- Parallel caps where exact values unavailable (e.g. 470 pF + 33 pF = 503 pF)
- Adjust inductance by spreading turns (increase L) or compressing (decrease L)
- Manhattan-style or ground plane PCB recommended
- At 5W: I_peak = sqrt(2 x 5 / 50) = 0.45A — no saturation concerns with T50 cores
