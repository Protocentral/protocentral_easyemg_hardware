# Protocentral easyEMG Breakout — Hardware

![Protocentral easyEMG Breakout](assets/protocentral-easyemg.jpg)

Open-source hardware design files for the **Protocentral easyEMG Breakout**, a single-channel surface EMG (sEMG) board on I²C / Qwiic. It's built from parts you can probe: a [TI INA333](https://www.ti.com/product/INA333) instrumentation amplifier, two [TI OPA2333](https://www.ti.com/product/OPA2333) op-amps and a [TI TLA2024](https://www.ti.com/product/TLA2024) 12-bit ADC.

Unlike an analog "muscle sensor", it outputs the **raw band-limited waveform** over I²C; the RMS envelope is computed in the library.

## Don't have one? [Buy it here](https://protocentral.com/product/easyemg-surface-emg-breakout-qwiic/)

## Links

| | |
|---|---|
| Product page | https://protocentral.com/product/easyemg-surface-emg-breakout-qwiic/ |
| Getting Started guide | https://protocentral.com/product/easyemg-surface-emg-breakout-qwiic/docs/getting-started/ |
| Arduino library | https://github.com/Protocentral/protocentral_easyemg_arduino |
| MicroPython / Raspberry Pi library | https://github.com/Protocentral/protocentral-micropython-easyemg |

## Specifications

- **Channels:** 1 surface EMG channel, 3 electrodes
- **Front end:** TI INA333 instrumentation amplifier, two TI OPA2333 op-amps, TI TLA2024 12-bit ADC
- **Gain:** ×51.7
- **Bandwidth:** about 20–310 Hz
- **Resolution:** about 2.42 µV per count at the electrodes
- **Input range:** about ±4.95 mV
- **Interface:** I²C / Qwiic, address 0x48 (0x49 via the ADDR jumper)
- **Connectors:** 2 × Qwiic / STEMMA QT, 3.5 mm electrode jack, 0.1" header
- **Supply:** 3.3 V on Qwiic; 3.3–5 V on the header
- **Board:** 40.0 × 28.8 mm

## Electrode connections

| Jack contact | Signal | Lead colour | Placement |
|---|---|---|---|
| Sleeve | **E1** | Green | muscle belly |
| Ring | **E2** | Red | muscle belly, ~20 mm from E1, along the fibres |
| Tip | **REF** | Yellow | bony landmark away from muscle: elbow or wrist |

Lead colours are for the 3-lead cable supplied in the kit.

## Repository layout

| Folder | Contents |
|---|---|
| [`hardware/`](hardware/) | KiCad project (schematic + PCB layout) and the exported [schematic PDF](hardware/protocentral-easyemg-schematic.pdf) |

## Revisions

| Revision | Date | Notes |
|---|---|---|
| v2 | 2026-10 | First release |

## Important notice

easyEMG is for research, education and evaluation only. It is **not a medical device** and has no FDA, CE or FCC approval. It has **no patient isolation**: with electrodes on a person, use a battery-powered host or an [easyISO isolated Qwiic adapter](https://protocentral.com/product/easyiso-isolated-qwiic-adapter/), and a battery-powered scope on the test points. A mains-earthed bench scope connects the person wearing the electrodes to earth.

## License

The hardware design files in this repository are licensed under the **CERN Open Hardware Licence Version 2 – Permissive (CERN-OHL-P v2)**. See [LICENSE](LICENSE).

The accompanying libraries (in the separate [protocentral_easyemg_arduino](https://github.com/Protocentral/protocentral_easyemg_arduino) and [protocentral-micropython-easyemg](https://github.com/Protocentral/protocentral-micropython-easyemg) repositories) are licensed under the MIT License.
