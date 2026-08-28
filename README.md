# Volutra

Volutra is an experimental Bafang e-bike programming and configuration tool.

It communicates with Bafang systems over CAN bus using a **CANable Pro**.

Volutra currently supports **Windows and Linux**.

---

## ⚠️ Experimental

> **Volutra is experimental software.**
>
> This software communicates directly with real e-bike hardware. Incorrect settings, wiring, firmware, or interrupted operations can cause problems with your bike or connected hardware.
>
> **Use it at your own risk.**
>
> It is recommended that you back up your original firmware and configuration before making changes.

---

## Requirements

### Hardware

**CANable Pro is required.**

Volutra is designed to communicate with the Bafang CAN bus through a CANable Pro.

You will need:

* [CANable Pro](https://nl.aliexpress.com/item/1005006331757235.html)
* USB-C cable
* [CAN bus connectors](https://nl.aliexpress.com/item/1005005307670708.html?gatewayAdapt=pol2nld)
* [Volutra](https://github.com/Mildspook/Volutra/releases)


### Software

**Node.js is required.**

Check that Node.js and npm are installed:

```bash
node --version
npm --version
```

---

## Wiring

The CANable Pro needs to be connected to the Bafang CAN bus.

### Reference wiring

<img width="1272" height="830" alt="Volutra CANable Pro wiring diagram" src="https://github.com/user-attachments/assets/a1467e45-30f8-4431-97e0-10e8d037f543" />

**Make sure you verify the wiring for your specific Bafang system before connecting anything.**

---

## Windows

Download the Windows version from the project's releases.

Install Volutra and connect your CANable Pro before using it with the bike.

---

## Linux

Download the Linux version from the project's releases.

If the release is an AppImage, make it executable:

```bash
chmod +x Volutra-*.AppImage
```

Then run it:

```bash
./Volutra-*.AppImage
```

---

## Compatibility

Volutra is intended for Bafang systems that communicate over CAN bus.

Compatibility can depend on the specific:

* Motor
* Controller
* Display
* Firmware
* Hardware revision

Not every Bafang system has been tested.

---

## Programming

Volutra can communicate with and modify connected Bafang hardware.

Before making changes:

* Back up the original configuration.
* Keep a copy of the original firmware where possible.
* Make sure the correct device is connected.
* Make sure the bike has stable power.
* Do not disconnect the CANable Pro during an operation.
* Do not interrupt firmware programming.

---

## Closed Source

Volutra is **closed-source software**.

The source code is not provided in this repository.

The software may not be modified, redistributed, or repackaged without permission from the developer.

---

## Credits

* **Mild_spook**

---

## Disclaimer

Volutra is experimental software provided as-is.

You are responsible for the hardware and systems you connect to Volutra.

**Use at your own risk.**
