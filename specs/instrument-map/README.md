# Spec draft: instrument identity → existing free and open-source software (FOSS)

Requirement [#10](https://github.com/linux-engineering-tools/community/issues/10). Human catalog: [`../../catalog/electronics.md`](../../catalog/electronics.md). Terms: [`../../TERMS.md`](../../TERMS.md).

**Status:** draft. Prefer a structured file **in this repo** plus a thin CLI. New instrument support still belongs in **libsigrok** or **lxi-tools**, not a LET driver tree.

## Job

Given a device identity, print the existing project and how to invoke it.

## Inputs

- USB VID:PID
- LXI `*IDN?` / mDNS service
- USBTMC, serial path, or GPIB address

## Outputs / standards

JSON: project name, URL, CLI invocation, capability (`log` / `set` / `decode`). Protocols: SCPI, LXI, USBTMC, usbmon, libsigrok driver names.

## CLI (proposed)

Binary not named `let`. Could live in `community` as a script later, or upstream in sigrok/lxi-tools.

```
instrument-map lookup --vidpid 1234:5678 --json
instrument-map lookup --idn 'EXAMPLE CO,PSU,1.0' --json
instrument-map lookup --dry-run --vidpid 1d6b:0002
```

`--dry-run` only reads the committed map; it does not touch USB.

### Exit codes

| Code | Meaning |
|---|---|
| 0 | Match |
| 2 | Bad args / map unreadable |
| 3 | No match (JSON `{ "ok": false, "matches": [] }`) |
| 64 | Usage |

## JSON (minimum)

```json
{
  "ok": true,
  "query": { "vidpid": "1d6b:0002" },
  "matches": [
    {
      "project": "usbmon",
      "url": "https://docs.kernel.org/usb/usbmon.html",
      "cli": "modprobe usbmon",
      "capability": ["log"]
    }
  ]
}
```

## Map source

Start from:

- [`catalog/electronics.md`](../../catalog/electronics.md)
- [sigrok supported hardware](https://sigrok.org/wiki/Supported_hardware)
- lxi-tools / PyVISA docs

The map is data (YAML or JSON) generated or hand-maintained. Do not scrape vendor GUIs.

## Acceptance tests

- Fixture VID:PID from a documented sigrok device → names `sigrok-cli` or PulseView as appropriate.
- Fixture `*IDN?` string for an LXI-class example → `lxi` or PyVISA invocation.
- Unknown id: exit 3, empty `matches`.
- Headless; no Super-key GUI.

## Upstream

Ask sigrok whether a machine-readable subset of “supported hardware” already exists (`libsigrok` scan). If yes, wrap it; do not fork the wiki.
