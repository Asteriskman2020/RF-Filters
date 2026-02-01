# 6m Band Low Pass Filter — 2W QRP

## Design Parameters
- **Band**: 6m (50.0–54.0 MHz)
- **Cutoff**: 60 MHz (Chebyshev 0.5dB ripple)
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
| C1 | 91 pF | **91 pF** | C0G/NP0 ceramic |
| L1 | 163 nH | **160 nH** | 7 turns on T37-6 |
| C2 | 135 pF | **130 pF** | C0G/NP0 ceramic |
| L2 | 163 nH | **160 nH** | 7 turns on T37-6 |
| C3 | 91 pF | **91 pF** | C0G/NP0 ceramic |

## Toroid Winding

- **Core**: T37-6 (yellow, AL = 3.0 nH/t^2)
- **Turns**: 7 turns of 22 AWG enameled wire
- **L** = 7^2 x 3.0 = **147 nH** (spread turns to reach ~160 nH)
- Keep leads as short as possible at VHF
- T37-6 is fine for 2W

## Expected Performance

| Frequency | Attenuation |
|-----------|-------------|
| 54.0 MHz (band edge) | < 0.5 dB |
| 108 MHz (2nd harmonic) | ~ -35 dB |
| 162 MHz (3rd harmonic) | ~ -55 dB |

## Parts List
- 2x T37-6 toroid (Amidon yellow)
- 22 AWG enameled magnet wire (~12 cm)
- 2x 91 pF C0G/NP0 ceramic capacitor (50V+)
- 1x 130 pF C0G/NP0 ceramic
- 2x SMA connectors

## VHF Build Notes
- At 50+ MHz, lead length and layout are critical
- Use ground plane PCB — Manhattan pads recommended
- Keep all component leads under 3 mm
- SMA connectors directly on board edges
