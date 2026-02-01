# 17m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 17m (18.068–18.168 MHz)
- **Cutoff**: 21 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 259 pF | **270 pF** | C0G/NP0 ceramic |
| L1 | 466 nH | **470 nH** | 13 turns on T37-6 |
| C2 | 385 pF | **390 pF** | C0G/NP0 ceramic |
| L2 | 466 nH | **470 nH** | 13 turns on T37-6 |
| C3 | 259 pF | **270 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T37-6 (yellow, AL = 3.0 nH/t^2)
- **Turns**: 13 turns of 26 AWG enameled wire
- **L** = 13^2 x 3.0 = **507 nH** (compress turns to lower to ~470 nH)
- T37-6 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 18.168 MHz (band edge) | < 0.5 dB |
| 36.3 MHz (2nd harmonic) | ~ -35 dB |
| 54.5 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T37-6 toroid (Amidon yellow)
- 26 AWG enameled magnet wire (~25 cm)
- 2x 270 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 390 pF C0G/NP0 ceramic
- 2x SMA connectors
