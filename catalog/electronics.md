# Electronics free and open-source software (FOSS) on Linux

Contribute **upstream** to these before incubating a Linux Engineering Tools (LET) tool. This map is the answer to “the tools exist but I cannot find them.” Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

Standards to prefer in requirements: Standard Commands for Programmable Instruments (SCPI / IEEE 488.2), LAN eXtensions for Instrumentation (LXI), USB Test and Measurement Class (USBTMC), General Purpose Interface Bus (GPIB, IEEE 488.1), USB (usbmon), Joint Test Action Group (JTAG) / Serial Wire Debug (SWD). Do not file clone-specs of vendor bench graphical user interfaces.

## Design (electronic design automation, EDA)

| Project | Job | Forge | Display |
|---|---|---|---|
| [KiCad](https://www.kicad.org/) | Schematic and PCB | [GitLab](https://gitlab.com/kicad/code/kicad) | `x11` |
| [Horizon EDA](https://horizon-eda.org/) | Schematic and PCB | [GitHub](https://github.com/horizon-eda/horizon) | `unverified` |
| [LibrePCB](https://librepcb.org/) | Schematic and PCB | [GitHub](https://github.com/LibrePCB/LibrePCB) | `unverified` |
| [ngspice](https://ngspice.sourceforge.io/) | Circuit simulation | [SourceForge](https://sourceforge.net/p/ngspice/ngspice/) | `cli` |
| [xschem](https://xschem.sourceforge.io/gtk.php) | Schematic capture (often IC) | [SourceForge](https://sourceforge.net/p/xschem/code/) | `unverified` |
| [Yosys](https://yosyshq.net/yosys/) | Logic synthesis (TUI) | [GitHub](https://github.com/YosysHQ/yosys) | `cli` |
| [GHDL](https://ghdl.github.io/ghdl/) | VHDL simulation | [GitHub](https://github.com/ghdl/ghdl) | `cli` |
| [Verilator](https://www.veripool.org/verilator/) | Verilog/SystemVerilog simulation | [GitHub](https://github.com/verilator/verilator) | `cli` |
| [Qucs-S](https://ra3xdh.github.io/) | Circuit simulation GUI over ngspice and others | [GitHub](https://github.com/ra3xdh/qucs_s) | `unverified` |
| [openEMS](https://openems.de/) | Electromagnetic FDTD | [GitHub](https://github.com/thliebig/openEMS) | `cli` |
| [scikit-rf](https://scikit-rf.org/) | Network / S-parameter analysis in Python | [GitHub](https://github.com/scikit-rf/scikit-rf) | `cli` |

KiCad GitHub is a **mirror**. Patches go to GitLab. Display evidence: [`desktop.md`](desktop.md).

High-frequency SI/PI and some IC DRC/bitstream jobs are still thin on Linux. Prefer **upstream** (KiCad, ngspice, openEMS) before a LET tool. Manufacturing interchange: prefer **IPC-2581** and Gerber X3 over vendor CAM databases.

## Instruments and signals (bench)

The [sigrok](https://sigrok.org/wiki/Main_Page) suite is the default home for logic analyzers, many scopes, DMMs, PSUs, loads, and protocol decode. Frontends: **sigrok-cli**, [PulseView](https://sigrok.org/wiki/PulseView) (LA/DSO), [SmuView](https://sigrok.org/wiki/SmuView) (DMM/PSU/load). Hardware list: [supported hardware](https://sigrok.org/wiki/Supported_hardware).

| Project | Job | Forge | Display |
|---|---|---|---|
| [sigrok](https://sigrok.org/) / libsigrok / sigrok-cli | Capture, decode, log, and control supported instruments | [sigrok git](https://sigrok.org/gitweb/?p=libsigrok.git) | `cli` |
| PulseView | GUI for logic / mixed-signal / some scopes | [sigrok git](https://sigrok.org/gitweb/?p=pulseview.git) | `unverified` |
| SmuView | GUI for multimeters, power supplies, electronic loads | [GitHub](https://github.com/knarfS/smuview) | `unverified` |
| [lxi-tools](https://github.com/lxi-tools/lxi-tools) | Discover and talk to LXI (LAN) instruments; SCPI | [GitHub](https://github.com/lxi-tools/lxi-tools) | `cli` |
| [PyVISA](https://pyvisa.readthedocs.io/) (+ pyvisa-py) | SCPI over USBTMC / LAN / serial without NI-VISA | [GitHub](https://github.com/pyvisa/pyvisa) | `cli` |
| [linux-gpib](https://linux-gpib.sourceforge.io/) | IEEE 488.1 controllers on Linux | [SourceForge](https://sourceforge.net/projects/linux-gpib/) | `cli` |
| [OpenHantek6022](https://github.com/OpenHantek/OpenHantek6022) | GUI for some Hantek USB scopes | [GitHub](https://github.com/OpenHantek/OpenHantek6022) | `unverified` |

New instrument support belongs in **libsigrok** or **lxi-tools**, not a LET fork.

## USB (host-side capture)

| Project | Job | Forge | Display |
|---|---|---|---|
| [usbmon](https://docs.kernel.org/usb/usbmon.html) | Kernel USB I/O trace | [Linux kernel](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git) | `cli` |
| [Wireshark USB](https://wiki.wireshark.org/CaptureSetup/USB) | Capture and class decode on Linux via usbmon | [GitLab](https://gitlab.com/wireshark/wireshark) | `unverified` |

This is host-controller sniffing, not a hardware USB protocol analyzer. Hardware analyzer support is a separate requirement.

## Embedded debug / repair

| Project | Job | Forge | Display |
|---|---|---|---|
| [OpenOCD](https://openocd.org/) | JTAG/SWD, flash, GDB server | [GitHub](https://github.com/openocd-org/openocd) | `cli` |
| sigrok PulseView | On-wire protocol decode (I2C, SPI, UART, …) once you have a LA | [sigrok git](https://sigrok.org/gitweb/?p=pulseview.git) | `unverified` |

## Parts / stock

| Project | Job | Forge | Display |
|---|---|---|---|
| [InvenTree](https://inventree.org/) | Parts, stock, BOM (repair shops and labs) | [GitHub](https://github.com/inventree/InvenTree) | `web` |
