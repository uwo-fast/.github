# Licensing policy

How FAST repositories are licensed. This is the organization-wide default — an
individual repository may state otherwise in its own `LICENSE` or `LICENSING.md`,
which takes precedence.

FAST publishes open-source hardware and software for science and sustainability.
The licences below are reciprocal by design: work built on a FAST project stays
available to the next person who needs it.

## The two tracks

**Pure software** — no hardware design files in the repository:

- Everything is `GPL-3.0-or-later`, in a root `LICENSE` file.

**Anything containing hardware design files** — schematics, PCB layouts,
mechanical CAD, drawings, or a bill of materials:

- Software and firmware — `GPL-3.0-or-later`
- Hardware design files and the outputs generated from them — `CERN-OHL-S-2.0`
- Parametric CAD source — `GPL-3.0-or-later`, and `CERN-OHL-S-2.0` as well where the
  project owns it outright; see [Parametric CAD](#parametric-cad) below, which is
  the case worth reading before choosing anything
- Documentation — we license documentation specific to software under
  `GPL-3.0-or-later` and documentation specific to hardware under `CERN-OHL-S-2.0`.
  A document covering both, and documentation specific to neither, is licensed under
  both, at the user's option
- Research data — `CC-BY-4.0`; see [Research data](#research-data)

Start from [`uwo-fast/repo-template`](https://github.com/uwo-fast/repo-template).
It ships both tracks: a pure-software repository deletes `LICENSES/` and
`LICENSING.md` and keeps the root `LICENSE`.

## File layout

| File | Contents |
| --- | --- |
| `LICENSE` | Full GPL-3.0 text, at the repository root |
| `LICENSES/GPL-3.0-or-later.txt` | Same text, under its SPDX identifier |
| `LICENSES/CERN-OHL-S-2.0.txt` | Full CERN-OHL-S-2.0 text |
| `LICENSING.md` | Plain-language summary of what applies where |

The root `LICENSE` holds the *software* licence deliberately. GitHub reports exactly
one licence per repository, and its detector currently reads only the root file,
matching it against known licence texts. So a repository whose root file is a prose
summary — or whose licence text has anything prepended to it — is reported as having
no licence at all. **Never add a preamble, an SPDX pointer, or a project notice to
the root `LICENSE`**; put those in `LICENSING.md` or the README, where they cost
nothing. Naming the files in `LICENSES/` by SPDX identifier is a step toward
[REUSE](https://reuse.software/), which additionally wants per-file SPDX headers or
a `REUSE.toml`.

## Parametric CAD

Parametric CAD — OpenSCAD, CadQuery, build123d — is both source code and hardware
design source, and CERN-OHL-S-2.0 treats it as the latter: "Source" includes
"digital code" (§1.3), "Make" includes "compiling" (§1.6), and the Complete Source
a maker must be given is the design "in the preferred form for making
modifications" (§1.8) — the `.scad`, not the exported mesh. Licensing generated
geometry under `CERN-OHL-S-2.0` while keeping its source outside that grant leaves
a licensee unable to satisfy §4. Source and output therefore travel together:

- **CAD with no GPL-licensed dependency** — license the source under **both**
  `GPL-3.0-or-later` and `CERN-OHL-S-2.0`, and the geometry, drawings and bill of
  materials generated from it under `CERN-OHL-S-2.0`. As the copyright holder you
  may grant both, and doing so costs nothing.
- **CAD that includes a GPL-licensed library** — license the whole chain
  `GPL-3.0-or-later`: source, geometry, drawings and BOM alike. NopSCADlib, which
  several FAST projects include, is `GPL-3.0-or-later`, and GPL-3.0 is not a
  Compatible Licence under CERN-OHL-S-2.0 §1.2, so the whole-work licensing that
  §3.3(d) requires cannot be granted over source entangled with it. Nor does such a
  library qualify as an Available Component: §1.7(b) reaches physical parts and
  tool distributions, not an included design library. The hardware track still
  covers that repository's electronics and any non-parametric mechanical design.

`GPL-3.0-or-later` is a legitimate licence for a hardware design — it is what much
of the 3D-printing world publishes under. What the second case gives up is
CERN-OHL-S's hardware-specific reciprocity, not openness.

## Research data

Measurement data, calibration sets, and test fixtures' expected outputs are not
software and not a hardware design; neither licence above reaches them usefully.
License research data `CC-BY-4.0`, or `CC0-1.0` where attribution would be
impractical for downstream aggregation, and say which in the repository's
`LICENSING.md`.

## Exceptions

- **`AGPL-3.0-or-later`** when the software is used over a network — a server, web
  app, or hosted analysis tool. Several FAST repositories already use it.
- **A permissive licence** (`MIT`, `BSD-3-Clause`, `Apache-2.0`) for a library meant
  to be embedded widely, where adoption matters more than reciprocity. Say so in
  the repository's README.
- **`CERN-OHL-W-2.0`** for a design intended to be embedded in larger systems that
  will not themselves be open. Prefer `-S` unless there is a reason.

## Existing repositories

This policy applies going forward. Relicensing an existing repository requires the
agreement of everyone holding copyright in it, so:

- Sole-author repositories can adopt it immediately.
- Multi-contributor repositories need each contributor's sign-off first.
- A public repository with **no** `LICENSE` file is all-rights-reserved — nobody
  can legally copy, build, or fork it. Those are the ones to fix first, and adding
  a first licence needs the same agreement.

## Contributions

Contributions are licensed under the terms of the repository receiving them; see
[`CONTRIBUTING.md`](CONTRIBUTING.md). In a dual-licensed repository, a contribution
is licensed under whichever of the two licences covers the files it touches, as set
out in that repository's `LICENSING.md`.
