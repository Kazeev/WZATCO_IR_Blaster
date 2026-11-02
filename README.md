# WZATCO IR Blaster

Importable **Flipper Zero `.ir` remote profile** for [IR Blaster Remote](https://github.com/iodn/android-ir-blaster) on Android phones with an infrared transmitter (including supported Xiaomi phones).

## Download and import

1. Download [WZATCO.ir](WZATCO.ir) using **Raw / Download raw file**.
2. Open **IR Blaster Remote** → **Settings** → **Backup** → **Import backup** and select `WZATCO.ir`.
3. Select **Settings** → **IR hardware & learning** → **IR Transmitter** → **Internal**.
4. Open the imported remote and test **Menu** or **Source** on an already-on projector, then **PowerOnOff**.

The profile has **16** buttons: PowerOnOff, Mute, Settings, Mode, Source, UpArrow, DownArrow, LeftArrow, RightArrow, OK, Menu, Home, Return, VolumeMinus, PlayPause, VolumePlus.

## Technical details

- Source: [Ashokatronix/wzatco, remote_patterns.dart](https://github.com/Ashokatronix/wzatco/blob/main/lib/remote_patterns.dart)
- Signals are converted directly from the source **Pronto Hex** waveforms to **Flipper Zero raw** timings in microseconds, using the Pronto timebase and the source carrier frequency (~38 kHz).
- The raw frames preserve the final gap. `LongPress` is a repeat frame, not a regular button, so it is excluded from the button set.
- Tested for **data format and conversion consistency only**. Compatibility with **WZATCO C3 without Android** is **not yet verified on hardware** and may vary by model revision.
- Does **not** import into Xiaomi Mi Remote. Use **IR Blaster Remote**.

## Verification

Each Pronto code contains a 32-bit command waveform. Conversion keeps the original pulse and space order, frequency, and timing (rounded to the nearest microsecond).

## Attribution

IR signal data originated in [Ashokatronix/wzatco](https://github.com/Ashokatronix/wzatco). This repository includes converted signals and documentation, not the original Flutter app.
