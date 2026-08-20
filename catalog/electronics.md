# Electronics FOSS on Linux

Contribute **upstream** to these before incubating a LET tool. This map is the answer to “the tools exist but I cannot find them.”

Standards to prefer in requirements: SCPI / IEEE 488.2, LXI, USBTMC, GPIB (IEEE 488.1), USB (usbmon), JTAG/SWD. Do not file clone-specs of vendor bench GUIs.

## Design (EDA)

| Project | Job |
|---|---|
| [KiCad](https://www.kicad.org/) | Schematic and PCB |
| [Horizon EDA](https://horizon-eda.org/) | Schematic and PCB |
| [LibrePCB](https://librepcb.org/) | Schematic and PCB |
| [ngspice](https://ngspice.sourceforge.io/) | Circuit simulation |
| [xschem](https://xschem.sourceforge.io/gtk.php) | Schematic capture (often IC) |

## Instruments and signals (bench)

The [sigrok](https://sigrok.org/wiki/Main_Page) suite is the default home for logic analyzers, many scopes, DMMs, PSUs, loads, and protocol decode. Frontends: **sigrok-cli**, [PulseView](https://sigrok.org/wiki/PulseView) (LA/DSO), [SmuView](https://sigrok.org/wiki/SmuView) (DMM/PSU/load). Hardware list: [supported hardware](https://sigrok.org/wiki/Supported_hardware).

| Project | Job |
|---|---|
| [sigrok](https://sigrok.org/) / libsigrok / sigrok-cli | Capture, decode, log, and control supported instruments |
| PulseView | GUI for logic / mixed-signal / some scopes |
| SmuView | GUI for multimeters, power supplies, electronic loads |
| [lxi-tools](https://github.com/lxi-tools/lxi-tools) | Discover and talk to LXI (LAN) instruments; SCPI |
| [PyVISA](https://pyvisa.readthedocs.io/) (+ pyvisa-py) | SCPI over USBTMC / LAN / serial without NI-VISA |
| [linux-gpib](https://linux-gpib.sourceforge.io/) | IEEE 488.1 controllers on Linux |
| [OpenHantek6022](https://github.com/OpenHantek/OpenHantek6022) | GUI for some Hantek USB scopes |

New instrument support belongs in **libsigrok** or **lxi-tools**, not a LET fork.

## USB (host-side capture)

| Project | Job |
|---|---|
| [usbmon](https://docs.kernel.org/usb/usbmon.html) | Kernel USB I/O trace |
| [Wireshark USB](https://wiki.wireshark.org/CaptureSetup/USB) | Capture and class decode on Linux via usbmon |

This is host-controller sniffing, not a hardware USB protocol analyzer. Hardware analyzer support is a separate requirement.

## Embedded debug / repair

| Project | Job |
|---|---|
| [OpenOCD](https://openocd.org/) | JTAG/SWD, flash, GDB server |
| sigrok PulseView | On-wire protocol decode (I2C, SPI, UART, …) once you have a LA |

## Parts / stock

| Project | Job |
|---|---|
| [InvenTree](https://inventree.org/) | Parts, stock, BOM (repair shops and labs) |
