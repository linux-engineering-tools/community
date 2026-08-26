# Electronics free and open-source software (FOSS) on Linux

Contribute **upstream** to these before incubating a Linux Engineering Tools (LET) tool. This map is the answer to “the tools exist but I cannot find them.” Terms: [`../TERMS.md`](../TERMS.md).

Standards to prefer in requirements: Standard Commands for Programmable Instruments (SCPI / IEEE 488.2), LAN eXtensions for Instrumentation (LXI), USB Test and Measurement Class (USBTMC), General Purpose Interface Bus (GPIB, IEEE 488.1), USB (usbmon), Joint Test Action Group (JTAG) / Serial Wire Debug (SWD). Do not file clone-specs of vendor bench graphical user interfaces.

## Design (electronic design automation, EDA)

| Project | Job |
|---|---|
| [KiCad](https://www.kicad.org/) | Schematic and PCB |
| [Horizon EDA](https://horizon-eda.org/) | Schematic and PCB |
| [LibrePCB](https://librepcb.org/) | Schematic and PCB |
| [ngspice](https://ngspice.sourceforge.io/) | Circuit simulation |
| [xschem](https://xschem.sourceforge.io/gtk.php) | Schematic capture (often IC) |
| [Yosys](https://yosyshq.net/yosys/) | Logic synthesis (TUI) |
| [GHDL](https://ghdl.github.io/ghdl/) | VHDL simulation |
| [Verilator](https://www.veripool.org/verilator/) | Verilog/SystemVerilog simulation |
| [Qucs-S](https://ra3xdh.github.io/) | Circuit simulation GUI over ngspice and others |
| [openEMS](https://openems.de/) | Electromagnetic FDTD |
| [scikit-rf](https://scikit-rf.org/) | Network / S-parameter analysis in Python |

High-frequency SI/PI and some IC DRC/bitstream jobs are still thin on Linux. Prefer **upstream** (KiCad, ngspice, openEMS) before a LET tool. Manufacturing interchange: prefer **IPC-2581** and Gerber X3 over vendor CAM databases.

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
