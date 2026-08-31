<div align="center">

<img width="120" height="120" alt="Volutra icon" src="https://github.com/user-attachments/assets/73819479-7c16-4ad4-885f-96067c069d71" />

# Volutra

Bafang e-bike programming and configuration, over CAN bus.

[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-a83882)](#installation)
[![Status](https://img.shields.io/badge/status-experimental-critical)](#-this-is-experimental)
[![Hardware](https://img.shields.io/badge/requires-CANable%20Pro-333333)](#what-youll-need)

</div>

Volutra talks directly to Bafang mid-drive systems over their CAN bus,
using a CANable Pro as the bridge between your computer and the bike. Read
live telemetry, tune controller parameters, and manage firmware — without
Bafang's official tooling.

<br>

## ⚠️ This is experimental

Volutra writes directly to real motor controllers. A bad write, a dropped
connection mid-flash, or the wrong parameter for your hardware revision can
leave a controller in a bad state — in the worst case, permanently.

This isn't a "click through the warning" disclaimer. Please actually:

- **Back up your current configuration and firmware** before changing anything.
- Never disconnect the CANable Pro or interrupt a write in progress.
- Assume your specific motor/controller/display/firmware combination hasn't
  been tested, unless you've confirmed otherwise.

Volutra is provided as-is, with no warranty. You're responsible for what
happens to your bike. If that's not a trade-off you're comfortable with,
this isn't ready for you yet.

<br>

## What you'll need

**A CANable Pro is required** — Volutra has no other way to reach the bike's
CAN bus.

- [CANable Pro](https://nl.aliexpress.com/item/1005006331757235.html) and a USB-C cable
- [CAN bus connectors](https://nl.aliexpress.com/item/1005005307670708.html?gatewayAdapt=pol2nld) to wire into the Bafang system
- [Node.js](https://nodejs.org) installed — check with `node --version` and `npm --version`
- The latest [Volutra release](https://github.com/Mildspook/Volutra/releases) for your OS

<br>

## Wiring

Wire the CANable Pro into the Bafang CAN bus before opening Volutra. The
diagram below is a reference point, not a guarantee — verify pinout against
your own motor/controller/display revision before connecting anything live.

<img width="1272" height="830" alt="Volutra CANable Pro wiring diagram" src="https://github.com/user-attachments/assets/a1467e45-30f8-4431-97e0-10e8d037f543" />

<br>

## Installation

**Windows** — download the installer from [Releases](https://github.com/Mildspook/Volutra/releases), run it, and connect your CANable Pro before launching Volutra.

**Linux** — download the AppImage from [Releases](https://github.com/Mildspook/Volutra/releases), then:

```bash
chmod +x Volutra-*.AppImage
./Volutra-*.AppImage
```

Raw AppImages don't register their own icon with your file manager or app
menu — that's normal Linux behavior, not a Volutra bug. Run the bundled
`install-linux.sh` once, or use [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher)
/ [Gear Lever](https://github.com/mijorus/gearlever), to fix that permanently.

<br>

## How this exists

Bafang doesn't publish their CAN protocol. There's no spec, no SDK, nothing
official to build against. What Volutra knows about the protocol was pieced
together by sniffing CAN bus traffic — first by tapping the wires between a
controller and Bafang's own **Besst** programmer to see what a legitimate
diagnostic session actually looks like on the bus, then by tapping the same
wires while the bike was being ridden, to capture what real-world telemetry
and live parameter traffic looks like outside of a diagnostic session.

That's the honest origin of this tool: reconstructed from observed traffic,
not from documentation. It's also exactly why the warning above isn't
boilerplate — every message Volutra sends is built from what was *inferred*
to be correct, not from anything Bafang confirmed.

<br>

## Compatibility

Bafang's CAN protocol isn't identical across every motor, controller,
display, and firmware combination out there. Volutra has been tested against
some of them, not all of them. If you're on hardware nobody's confirmed yet,
go slowly, watch what each write actually does, and don't assume the tool
knows your setup better than you do.

<br>

## Help expand compatibility

Since the protocol was built by watching traffic rather than reading a spec,
the fastest way this project gets better is more traffic to look at. If
Volutra half-works, doesn't recognize a parameter, or you're running hardware
that isn't confirmed yet — the built-in CAN sniffer can log the raw frames
your system actually sends. A capture from an untested motor/controller/
display combo, ideally alongside what the official Besst tool does with the
same hardware, is genuinely useful and can turn into real support for that
hardware.

Bug reports without hardware details (motor, controller, display, firmware
version) are hard to act on — the more specific, the better.

<br>

## Before you flash anything

- Confirm the correct device is connected — don't assume.
- Keep the bike on stable, sufficient power for the whole operation.
- Never interrupt a firmware write once it's started. An interrupted flash
  can brick the controller.
- Keep your backups somewhere you'll actually find them again.

<br>

## License

**MSCS**

## Credits

Built by **mild_spook**.

## Get in touch

Questions, bug reports, or a sniffer capture from hardware that isn't
working yet — reach out on Discord: **mild_spook**.

---

<div align="center">
<sub>Volutra is experimental software provided as-is, with no warranty of any kind. Use at your own risk.</sub>
</div>
