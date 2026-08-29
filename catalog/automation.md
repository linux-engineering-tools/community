# Control / automation free and open-source software (FOSS) on Linux

Industrial input/output (I/O), open programmable-logic-controller (PLC) runtimes, and motion. Contribute **upstream**. Columns: [`README.md`](README.md). Terms: [`../TERMS.md`](../TERMS.md).

Vendor **safety** runtimes and certified SIL stacks are not LET clones. Jobs must cite IEC 61131-3, IEC 61499, EtherCAT (ETG), Modbus, or OPC UA.

| Project | Job | Forge | Display |
|---|---|---|---|
| [LinuxCNC](https://linuxcnc.org/) | Motion control (also `catalog/fabrication.md`) | [GitHub](https://github.com/LinuxCNC/linuxcnc) | `unverified` |
| [IgH EtherCAT Master](https://etherlab.org/ethercat/) | EtherCAT master on Linux | [GitLab](https://gitlab.com/etherlab.org/ethercat) | `cli` |
| [OpenPLC](https://autonomylogic.com/) | IEC 61131-3 runtime | [GitHub](https://github.com/thiagoralves/OpenPLC_v3) | `cli` |
| [Beremiz](https://beremiz.org/) | IEC 61131-3 IDE / runtime | [GitHub](https://github.com/beremiz/beremiz) | `unverified` |
| [open62541](https://www.open62541.org/) | OPC UA stack | [GitHub](https://github.com/open62541/open62541) | `cli` |

Fieldbus **hardware** chip quirks are not a reason to incubate a new stack; fix the driver or document the constraint.
