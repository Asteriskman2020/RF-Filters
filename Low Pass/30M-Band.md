# 30m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 30m (10.1–10.15 MHz)
- **Cutoff**: 12 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 453 pF | **470 pF** | C0G/NP0 ceramic |
| L1 | 815 nH | **820 nH** | 17 turns on T37-6 |
| C2 | 674 pF | **680 pF** | C0G/NP0 ceramic |
| L2 | 815 nH | **820 nH** | 17 turns on T37-6 |
| C3 | 453 pF | **470 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T37-6 (yellow, AL = 3.0 nH/t^2)
- **Turns**: 17 turns of 26 AWG enameled wire
- **L** = 17^2 x 3.0 = **867 nH** (compress slightly to reach ~820 nH)
- T37-6 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 10.15 MHz (band edge) | < 0.5 dB |
| 20.3 MHz (2nd harmonic) | ~ -35 dB |
| 30.45 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T37-6 toroid (Amidon yellow)
- 26 AWG enameled magnet wire (~30 cm)
- 2x 470 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 680 pF C0G/NP0 ceramic
- 2x SMA connectors
