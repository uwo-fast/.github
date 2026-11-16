# Contributing to FAST projects

Thanks for your interest in contributing to a **Free Appropriate Sustainable
Technology (FAST)** project! This is the organization-wide default guide — an
individual repository may provide its own `CONTRIBUTING.md` that takes precedence.

FAST projects are open-source hardware and software for science and sustainability.
Contributions of code, firmware, CAD, documentation, test data, and issue reports
are all welcome.

## Ways to contribute

- **Report a problem** — open an [issue](../../issues) using the bug report template.
- **Request a feature or design change** — open an issue using the feature request template.
- **Improve documentation** — fix typos, clarify build/assembly steps, add references.
- **Submit changes** — open a pull request (see below).

## Reporting issues

Before opening a new issue, search existing issues to avoid duplicates. A good
report includes:

- What you expected to happen and what actually happened.
- Steps to reproduce (for software/firmware) or the affected part/revision (for hardware).
- Your environment: OS, toolchain/library versions, board or hardware revision.
- Logs, photos, or screenshots where relevant.

## Before you open a pull request

FAST projects are physical engineering: a change here ends up in a part someone
prints, machines, or wires up. Every pull request costs a maintainer review time.

- **Understand the project first.** Open a pull request only for a concrete,
  justified improvement you can explain. Open source is not a
  contribution-counting exercise.
- **AI assistance is fine; contribution farming is not.** Using AI tools to make a
  genuine improvement is welcome. Automated pull requests from someone who has not
  engaged with the codebase are not.
- **Discuss non-trivial changes in an issue first.** A change to code, firmware,
  CAD, or a design needs a linked issue where the approach was discussed. Typo and
  documentation fixes can go straight to a pull request.
- **Physically validate your change, or offer to.** Build, print, or bench-test
  what you changed, and say what you did.
- **If you cannot validate it, open a draft.** Say plainly that the change has not
  been physically validated and ask for maintainer review. It is not ready to merge
  until that review is done.

Pull requests that do not follow this may be closed without a detailed review.

## Submitting changes (pull requests)

1. Fork the repository and create a topic branch off `main`.
2. Make focused, single-purpose changes — keep unrelated changes in separate PRs.
3. Follow the existing style and structure of the repository you're working in.
4. Validate your change and describe how in the PR description. A CAD render, a
   simulation, or a passing build is not physical validation.
5. Link the issue where a non-trivial change was discussed (e.g. "Closes #12").
   Typo and documentation fixes do not need one.
6. Open the pull request against `main` and fill out the PR template. If the change
   has not been physically validated, open it as a draft and say so.

## Commit messages

Write clear, imperative-mood commit subjects (e.g. "fix load-cell tare drift").
Keep the subject concise and put detail in the body when needed.

## Licensing

Unless a repository states otherwise, contributions are made under that
repository's `LICENSE`. By contributing, you agree your contributions are
licensed under those same terms.

Repositories that contain hardware designs are licensed separately by component —
`GPL-3.0-or-later` for software, firmware, and parametric CAD source, and
`CERN-OHL-S-2.0` for hardware design files and the outputs generated from them.
Separately by component, not dual-licensed: you do not get to choose which of the
two covers a given file. A contribution there is licensed under whichever licence
covers the files it touches, as set out in that repository's `LICENSING.md`. See the
organization [licensing policy](LICENSING.md) for how the two tracks are chosen.

## Code of conduct

Participation is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). Please
be respectful and constructive.

## Questions and collaboration

- For usage questions and help, see [SUPPORT.md](SUPPORT.md).
- For research collaboration inquiries, contact Dr. Joshua Pearce at
  <joshua.pearce@uwo.ca>.
