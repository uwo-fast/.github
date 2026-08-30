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

- Software, firmware, and parametric CAD source — `GPL-3.0-or-later`
- Hardware design files and the outputs generated from them — `CERN-OHL-S-2.0`
- Documentation — follows the component it documents; documentation that is
  specific to neither is dual-licensed, at the user's option

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

The root `LICENSE` holds the *software* licence deliberately. GitHub reports
exactly one licence per repository — it reads a root `LICENSE` file whose text
matches a known licence and does not scan `LICENSES/` — so a repository whose
root file is a prose summary is reported as having no licence at all. Naming the
files by SPDX identifier also keeps them compatible with
[REUSE](https://reuse.software/) if we ever want to lint them.

## Parametric CAD is source code

OpenSCAD, CadQuery, and build123d files are `GPL-3.0-or-later`, not
`CERN-OHL-S-2.0`. They are compiled rather than drawn, and they routinely include
GPL-licensed libraries — NopSCADlib, which several FAST projects depend on, is
GPL-3.0 — and `CERN-OHL-S-2.0` cannot be combined with GPL-3.0 in a single work.

The geometry those sources generate — STL, STEP, 3MF — together with the drawings
and bill of materials derived from it, is the repository's own hardware design and
is `CERN-OHL-S-2.0`. Where a generated output incorporates geometry from a
third-party GPL library, that output stays `GPL-3.0-or-later`.

## Exceptions

- **`AGPL-3.0-or-later`** when the software is used over a network — a server, web
  app, or hosted analysis tool. Already in use in `OpenReactor2`,
  `OS-Mechanical-Tester`, and `well-plate-guide`.
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
