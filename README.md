# OWL2.O — NOVA OS development

This repository is the canonical home for the NOVA operating-system project.

## Current source package

The complete NOVA 0.2.0-dev source tree is included in [NOVA-v0.2.0-source.zip](./NOVA-v0.2.0-source.zip). It contains the language frontend, bytecode format, reference VM, NOVA-LINK prototype, architecture specifications, x86-64 freestanding kernel sources, tests, build scripts, and pinned Limine protocol subset.

Extract it before working:

- Windows PowerShell: `Expand-Archive .\NOVA-v0.2.0-source.zip -DestinationPath .\`
- Linux/macOS: `unzip NOVA-v0.2.0-source.zip`

Then enter `NOVA-v0.2.0-dev` and follow its README.

## Validation

GitHub Actions runs the Python toolchain tests, kernel-core tests, PMM tests, builds the freestanding kernel ELF with Clang/LLD, and checks the ELF's exported architectural symbols.

QEMU is the next runtime-validation layer. It is not a deployment target: NOVA is a bootable-system project, not a web app. Vercel is not required.

## Project guardrails

- Keep the hybrid strategy: binary-compatible hardware support now; room for alternative execution backends later.
- Separate language design (NOVA.Sys / NOVA.App / NOVA.Flow), compiler IR, instruction-set proposals, and device communication protocols.
- Do not claim ARM64/mobile support or a production-ready OS before the relevant hardware and boot tests pass.
- Preserve deterministic tests and update architecture documentation alongside code.

## Design

[Editable NOVA OS desktop/mobile Figma file](https://www.figma.com/design/z6C8QvTasjAKzGyWdnM8dH).
