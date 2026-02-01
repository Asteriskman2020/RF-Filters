# Multi-Band Switched LPF — 20m / 17m / 10m / 6m — 100W

## Design Overview
- **Bands**: 20m, 17m, 10m, 6m
- **Power**: 100W (V_peak = 100V, I_peak = 2A)
- **Topology**: 4x 5-element Chebyshev 0.5dB ripple, relay-switched
- **Impedance**: 50 ohm
- **Switching**: 5x DPDT relays (12V coil)
- **Capacitors**: Silver mica or 500V C0G/NP0
- **Toroids**: T68-6 (yellow) with 18 AWG wire
- **Board**: single 100x60 mm PCB

## Block Diagram

```
            ┌─[K1]─── 20m LPF ───[K1]─┐
            │                          │
IN ──[K0]───┼─[K2]─── 17m LPF ───[K2]─┼───[K0]── OUT
     (bypass)│                          │  (bypass)
            ├─[K3]─── 10m LPF ───[K3]─┤
            │                          │
            └─[K4]─── 6m LPF  ───[K4]─┘

K0 = bypass relay (energized = filter mode, de-energized = straight through)
K1-K4 = band select relays (only one energized at a time)
```

## Relay Switching Detail

```
         IN                                              OUT
          │                                               │
          ├──K0a─NC──────────────────────────K0b─NC───────┤  (bypass path)
          │      │                                 │      │
          │      NO                                NO     │
          │      │                                 │      │
          │      ├──K1a─NO── [20m LPF] ──K1b─NO───┤      │
          │      │                                 │      │
          │      ├──K2a─NO── [17m LPF] ──K2b─NO───┤      │
          │      │                                 │      │
          │      ├──K3a─NO── [10m LPF] ──K3b─NO───┤      │
          │      │                                 │      │
          │      └──K4a─NO── [6m  LPF] ──K4b─NO───┘      │
          │                                               │
         GND                                             GND
```

- **K0 de-energized**: signal bypasses all filters (straight through)
- **K0 energized + K1 energized**: 20m filter active
- **K0 energized + K2 energized**: 17m filter active
- **K0 energized + K3 energized**: 10m filter active
- **K0 energized + K4 energized**: 6m filter active

## Each LPF Schematic

```
IN o───┬───[L1]───┬───[L2]───┬───o OUT
       │          │          │
      C1         C2         C3
       │          │          │
      GND        GND        GND
```

---

## 20m Band (14.0–14.35 MHz) — Cutoff 16 MHz

| Part | Calculated | Practical | Rating |
|------|-----------|-----------|--------|
| C1 | 339 pF | **330 pF** | 500V silver mica |
| L1 | 612 nH | **607 nH** | 9t on T68-6 |
| C2 | 506 pF | **500 pF** (470+33) | 500V silver mica |
| L2 | 612 nH | **607 nH** | 9t on T68-6 |
| C3 | 339 pF | **330 pF** | 500V silver mica |

- T68-6: AL = 7.5 nH/t^2, L = 9^2 x 7.5 = **607 nH**
- 18 AWG enameled wire, 9 turns evenly spaced
- 2nd harmonic (28 MHz): ~-35 dB | 3rd (42 MHz): ~-55 dB

---

## 17m Band (18.068–18.168 MHz) — Cutoff 21 MHz

| Part | Calculated | Practical | Rating |
|------|-----------|-----------|--------|
| C1 | 259 pF | **270 pF** | 500V silver mica |
| L1 | 466 nH | **480 nH** | 8t on T68-6 |
| C2 | 385 pF | **390 pF** (330+56) | 500V silver mica |
| L2 | 466 nH | **480 nH** | 8t on T68-6 |
| C3 | 259 pF | **270 pF** | 500V silver mica |

- T68-6: AL = 7.5 nH/t^2, L = 8^2 x 7.5 = **480 nH**
- 18 AWG enameled wire, 8 turns evenly spaced
- 2nd harmonic (36.3 MHz): ~-35 dB | 3rd (54.5 MHz): ~-55 dB

---

## 10m Band (28.0–29.7 MHz) — Cutoff 34 MHz

| Part | Calculated | Practical | Rating |
|------|-----------|-----------|--------|
| C1 | 160 pF | **150 pF** | 500V silver mica |
| L1 | 288 nH | **270 nH** | 6t on T68-6 |
| C2 | 238 pF | **220 pF + 18 pF** | 500V silver mica |
| L2 | 288 nH | **270 nH** | 6t on T68-6 |
| C3 | 160 pF | **150 pF** | 500V silver mica |

- T68-6: AL = 7.5 nH/t^2, L = 6^2 x 7.5 = **270 nH**
- 18 AWG enameled wire, 6 turns spread for ~288 nH
- 2nd harmonic (59.4 MHz): ~-35 dB | 3rd (89.1 MHz): ~-55 dB

---

## 6m Band (50.0–54.0 MHz) — Cutoff 60 MHz

| Part | Calculated | Practical | Rating |
|------|-----------|-----------|--------|
| C1 | 91 pF | **91 pF** | 500V silver mica |
| L1 | 163 nH | **168 nH** | 5t on T68-6 |
| C2 | 135 pF | **130 pF** | 500V silver mica |
| L2 | 163 nH | **168 nH** | 5t on T68-6 |
| C3 | 91 pF | **91 pF** | 500V silver mica |

- T68-6: AL = 7.5 nH/t^2, L = 5^2 x 7.5 = **187 nH** (compress to ~168 nH)
- 18 AWG enameled wire, 5 turns compressed
- Keep leads under 3 mm — VHF layout critical
- 2nd harmonic (108 MHz): ~-35 dB | 3rd (162 MHz): ~-55 dB

---

## Quick Reference

| Band | Cutoff | C1/C3 | C2 | Turns | L actual |
|------|--------|-------|----|-------|----------|
| 20m | 16 MHz | 330 pF | 500 pF | 9t | 607 nH |
| 17m | 21 MHz | 270 pF | 390 pF | 8t | 480 nH |
| 10m | 34 MHz | 150 pF | 238 pF | 6t | 270 nH |
| 6m | 60 MHz | 91 pF | 130 pF | 5t | 168 nH |

All inductors: T68-6 (yellow), 18 AWG enameled wire

---

## Relay Selection

For 100W RF switching, use relays rated for RF service:

| Option | Type | Coil | Contact Rating | Notes |
|--------|------|------|----------------|-------|
| **Omron G5RL-1A-E** | SPDT | 12V | 16A / 250VAC | Good RF, low cost |
| **Hongfa HFD2/012** | DPDT | 12V | 2A / 250VAC | Compact, adequate |
| **Axicom IM03** | DPDT | 12V | 2A | True RF relay |
| **Tianbo TRA2 L-12VDC** | DPDT | 12V | 1A RF | Common in ham gear |

- Need 5 DPDT relays (K0 bypass + K1-K4 band select)
- Or 10 SPDT relays (2 per filter + 2 for bypass)
- Add flyback diodes (1N4148) across all relay coils

---

## Control Interface

### Simple Toggle Switch Control
```
+12V ──┬──[SW0]──── K0 coil ──── GND    (bypass/filter)
       ├──[SW1]──── K1 coil ──── GND    (20m)
       ├──[SW2]──── K2 coil ──── GND    (17m)
       ├──[SW3]──── K3 coil ──── GND    (10m)
       └──[SW4]──── K4 coil ──── GND    (6m)
```

### MCU Control (ESP32/Arduino)
```
GPIO ──[2N2222]──── Relay coil ──── +12V
           │
          4.7k
           │
          GND

Use ULN2003 Darlington array for driving all 5 relays from MCU.
Band select via serial command, PTT, or CAT interface.
```

---

## PCB Layout (100 x 60 mm)

```
┌──────────────────────────────────────────────────────────────┐
│  SMA    K0a                                    K0b    SMA   │
│  IN  ○──┤├──┬───────────────────────────────┬──┤├──○  OUT   │
│              │                               │              │
│         K1a ┤├── C1  L1  C2  L2  C3 ──┤├ K1b    [20m]     │
│              │                               │              │
│         K2a ┤├── C1  L1  C2  L2  C3 ──┤├ K2b    [17m]     │
│              │                               │              │
│         K3a ┤├── C1  L1  C2  L2  C3 ──┤├ K3b    [10m]     │
│              │                               │              │
│         K4a ┤├── C1  L1  C2  L2  C3 ──┤├ K4b    [6m]      │
│              │                               │              │
│  ┌───────────┴───────────────────────────────┘              │
│  │  GROUND PLANE (continuous, unbroken copper)              │
│  │                                                          │
│  │  [K0] [K1] [K2] [K3] [K4]    [12V]  [BAND SEL HEADER]  │
│  │  relay row with flyback diodes        control connector  │
│  └──────────────────────────────────────────────────────────│
└──────────────────────────────────────────────────────────────┘
```

### Layout Rules for 100W
- **Unbroken ground plane** on bottom layer — no cuts, no traces
- Signal traces: 2 mm minimum width (50 ohm microstrip)
- Keep each filter section isolated — no coupling between bands
- Toroids mounted flat, spaced at least 1x diameter apart
- SMA connectors at board edges, ground pins soldered to plane
- Relay coil traces on top layer, away from RF path
- Capacitors: radial leads, soldered flush to ground plane
- Add ground vias around each filter section

---

## Bill of Materials

| Qty | Part | Value | Package | Notes |
|-----|------|-------|---------|-------|
| 2 | Silver mica cap | 330 pF / 500V | radial | 20m C1/C3 |
| 1 | Silver mica cap | 470 pF / 500V | radial | 20m C2 (+ 33pF) |
| 1 | Silver mica cap | 33 pF / 500V | radial | 20m C2 parallel |
| 2 | Silver mica cap | 270 pF / 500V | radial | 17m C1/C3 |
| 1 | Silver mica cap | 330 pF / 500V | radial | 17m C2 (+ 56pF) |
| 1 | Silver mica cap | 56 pF / 500V | radial | 17m C2 parallel |
| 2 | Silver mica cap | 150 pF / 500V | radial | 10m C1/C3 |
| 1 | Silver mica cap | 220 pF / 500V | radial | 10m C2 (+ 18pF) |
| 1 | Silver mica cap | 18 pF / 500V | radial | 10m C2 parallel |
| 2 | Silver mica cap | 91 pF / 500V | radial | 6m C1/C3 |
| 1 | Silver mica cap | 130 pF / 500V | radial | 6m C2 |
| 8 | T68-6 toroid | yellow | — | 2 per band |
| 1 | 18 AWG enameled wire | — | — | ~1.5 m total |
| 5 | DPDT relay | 12V coil | — | K0-K4 |
| 5 | 1N4148 diode | — | DO-35 | flyback protection |
| 2 | SMA connector | 50 ohm | edge mount | IN / OUT |
| 1 | 2-pin header | 12V power | — | relay supply |
| 1 | 5-pin header | band select | — | control lines |
| 1 | PCB | 100x60 mm | FR4 1.6mm | double-sided copper |

**Total capacitors**: 14 silver mica
**Total toroids**: 8x T68-6
**Total relays**: 5x DPDT

---

## 100W Design Notes

- **Capacitors**: Silver mica 500V rated — do NOT use ceramic at 100W (risk of cracking under RF stress). Alternative: ATC porcelain RF caps.
- **Toroids**: T68-6 handles 100W without saturation. Core loss is negligible. 18 AWG wire handles 2A peak current with margin.
- **Relays**: ensure relay contacts are rated for RF. Mechanical relays with gold-plated contacts preferred. Hot-switching (switching under RF power) will arc and damage contacts — always switch during TX off.
- **Trace width**: 2 mm minimum for 50 ohm on 1.6 mm FR4 (Er=4.6). Use PCB calculator to verify.
- **Insertion loss**: expect < 0.3 dB per filter at 100W.
- **Never energize two band relays simultaneously** — will create undefined filter response.
