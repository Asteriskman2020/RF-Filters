# 80m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 80m (3.5–4.0 MHz)
- **Cutoff**: 5.0 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 1086 pF | **1000 pF + 100 pF** | parallel, C0G/NP0 |
| L1 | 1957 nH | **2.0 uH** | 20 turns on T50-2 |
| C2 | 1617 pF | **1500 pF + 120 pF** | parallel, C0G/NP0 |
| L2 | 1957 nH | **2.0 uH** | 20 turns on T50-2 |
| C3 | 1086 pF | **1000 pF + 100 pF** | parallel, C0G/NP0 |

## Toroid Winding

- **Core**: T50-2 (red, AL = 4.9 nH/t^2)
- **Turns**: 20 turns of 26 AWG enameled wire
- **L** = 20^2 x 4.9 = **1960 nH** (close to target)
- T50-2 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 4.0 MHz (band edge) | < 0.5 dB |
| 8.0 MHz (2nd harmonic) | ~ -35 dB |
| 12.0 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T50-2 toroid (Amidon red)
- 26 AWG enameled magnet wire (~50 cm)
- 2x 1000 pF C0G/NP0 ceramic capacitor (50V+)
- 2x 100 pF C0G/NP0 ceramic
- 1x 1500 pF C0G/NP0 ceramic
- 1x 120 pF C0G/NP0 ceramic
- 2x SMA connectors
