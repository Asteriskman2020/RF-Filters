# 10m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 10m (28.0–29.7 MHz)
- **Cutoff**: 34 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 160 pF | **150 pF** | C0G/NP0 ceramic |
| L1 | 288 nH | **290 nH** | 10 turns on T37-6 |
| C2 | 238 pF | **220 pF + 18 pF** | parallel, C0G/NP0 |
| L2 | 288 nH | **290 nH** | 10 turns on T37-6 |
| C3 | 160 pF | **150 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T37-6 (yellow, AL = 3.0 nH/t^2)
- **Turns**: 10 turns of 26 AWG enameled wire
- **L** = 10^2 x 3.0 = **300 nH** (compress turns slightly to reach ~290 nH)
- T37-6 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 29.7 MHz (band edge) | < 0.5 dB |
| 59.4 MHz (2nd harmonic) | ~ -35 dB |
| 89.1 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T37-6 toroid (Amidon yellow)
- 26 AWG enameled magnet wire (~18 cm)
- 2x 150 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 220 pF C0G/NP0 ceramic
- 1x 18 pF C0G/NP0 ceramic
- 2x SMA connectors
