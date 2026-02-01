# 160m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 160m (1.8–2.0 MHz)
- **Cutoff**: 2.5 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 2172 pF | **2200 pF** | C0G/NP0 ceramic |
| L1 | 3914 nH | **3.9 uH** | 28 turns on T50-2 |
| C2 | 3235 pF | **3300 pF** | C0G/NP0 ceramic |
| L2 | 3914 nH | **3.9 uH** | 28 turns on T50-2 |
| C3 | 2172 pF | **2200 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T50-2 (red, AL = 4.9 nH/t^2)
- **Turns**: 28 turns of 26 AWG enameled wire
- **L** = 28^2 x 4.9 = **3841 nH** (spread turns to reach ~3.9 uH)
- T50-2 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 2.0 MHz (band edge) | < 0.5 dB |
| 4.0 MHz (2nd harmonic) | ~ -35 dB |
| 6.0 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T50-2 toroid (Amidon red)
- 26 AWG enameled magnet wire (~80 cm)
- 2x 2200 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 3300 pF C0G/NP0 ceramic
- 2x SMA connectors
