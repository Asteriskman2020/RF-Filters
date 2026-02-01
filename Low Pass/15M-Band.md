# 15m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 15m (21.0–21.45 MHz)
- **Cutoff**: 25 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 217 pF | **220 pF** | C0G/NP0 ceramic |
| L1 | 391 nH | **390 nH** | 11 turns on T37-6 |
| C2 | 323 pF | **330 pF** | C0G/NP0 ceramic |
| L2 | 391 nH | **390 nH** | 11 turns on T37-6 |
| C3 | 217 pF | **220 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T37-6 (yellow, AL = 3.0 nH/t^2)
- **Turns**: 11 turns of 26 AWG enameled wire
- **L** = 11^2 x 3.0 = **363 nH** (spread turns to reach ~390 nH)
- T37-6 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 21.45 MHz (band edge) | < 0.5 dB |
| 42.9 MHz (2nd harmonic) | ~ -35 dB |
| 64.4 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T37-6 toroid (Amidon yellow)
- 26 AWG enameled magnet wire (~20 cm)
- 2x 220 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 330 pF C0G/NP0 ceramic
- 2x SMA connectors
