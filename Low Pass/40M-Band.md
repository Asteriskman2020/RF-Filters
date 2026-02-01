# 40m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 40m (7.0–7.3 MHz)
- **Cutoff**: 8.5 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 639 pF | **680 pF** | C0G/NP0 ceramic |
| L1 | 1151 nH | **1.15 uH** | 17 turns on T50-6 |
| C2 | 952 pF | **1000 pF** | C0G/NP0 ceramic |
| L2 | 1151 nH | **1.15 uH** | 17 turns on T50-6 |
| C3 | 639 pF | **680 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T50-6 (yellow, AL = 4.0 nH/t^2)
- **Turns**: 17 turns of 26 AWG enameled wire
- **L** = 17^2 x 4.0 = **1156 nH** (very close to target)
- T50-6 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 7.3 MHz (band edge) | < 0.5 dB |
| 14.6 MHz (2nd harmonic) | ~ -35 dB |
| 21.9 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T50-6 toroid (Amidon yellow)
- 26 AWG enameled magnet wire (~40 cm)
- 2x 680 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 1000 pF C0G/NP0 ceramic
- 2x SMA connectors
