# 20m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 20m (14.0–14.35 MHz)
- **Cutoff**: 16 MHz (Chebyshev 0.5dB ripple)
- **Order**: 5-element (3 caps, 2 inductors)
- **Impedance**: 50 ohm
- **Power**: 2W

## Schematic

```
IN o───┬───[L1]───┬───[L2]───┬───o OUT
       │          │          │
      C1         C2         C3
       │          │          │
      GND        GND        GND
```

## Component Values

| Part | Calculated | Practical Value | Notes |
|------|-----------|----------------|-------|
| C1 | 339 pF | **330 pF** | C0G/NP0 ceramic |
| L1 | 612 nH | **610 nH** | 14 turns on T37-6 |
| C2 | 506 pF | **470 pF + 33 pF** | parallel, C0G/NP0 |
| L2 | 612 nH | **610 nH** | 14 turns on T37-6 |
| C3 | 339 pF | **330 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T37-6 (yellow, AL = 3.0 nH/t^2)
- **Turns**: 14 turns of 26 AWG enameled wire
- **L** = 14^2 x 3.0 = **588 nH** (spread turns slightly to reach ~610 nH)
- T37-6 is fine for 2W — no heating concerns

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 14.35 MHz (band edge) | < 0.5 dB |
| 28 MHz (2nd harmonic) | ~ -35 dB |
| 42 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T37-6 toroid (Amidon yellow)
- 26 AWG enameled magnet wire (~30 cm)
- 2x 330 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 470 pF C0G/NP0 ceramic
- 1x 33 pF C0G/NP0 ceramic
- 2x SMA connectors (or direct solder)

## Build Tips
- Use **C0G/NP0** caps only — X7R drifts with temperature and is lossy at RF
- Wind toroids evenly spaced around ~270 degrees of the core
- Keep leads short — stray inductance matters at 14 MHz
- Ground plane PCB or Manhattan-style on copper clad board
- At 2W, 50V-rated caps are sufficient (V_peak = sqrt(2 x 2 x 50) = 14V)
