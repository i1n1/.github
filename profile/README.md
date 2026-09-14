<div align="center">

<img src="assets/nextcore-brand-board.png" alt="NextCore — symbol, wordmark, and interface examples" width="1120">

# NEXTCORE

**Boot · Config · Recovery · Docs**

macOS compatibility on x86 EFI — UEFI boot, HAL translation, and Metal acceleration
development for macOS 26 Tahoe and macOS 27 Golden Gate.

</div>

---

## Overview

Home of the **26x86** organization: NextCore source modules, integration tooling,
development docs, and brand resources.

Code and docs track measured implementation status. Install steps, supported
environments, and release notes live in each repository — not on this profile page.

> **Experimental.** A passed static check, emulator probe, or firmware transfer is
> never presented as a physical-Mac or macOS boot result.
> `macos_boot_verified` stays false until target-matching XNU and userspace
> evidence are published.

## Release 1.0.0

**1.0.0** is the packaging and absorb milestone for the NextCore module family:
aligned public docs, binary export surface, and independently versioned crates
under the `26x86` organization. It does **not** claim a verified macOS boot.

| Milestone | Meaning |
| --- | --- |
| **1.0.0** | Absorb / packaging release — modules, docs, and binary metadata aligned |
| **2.0.0** | Reserved until macOS 27 boot is verified with honest UART evidence |

Public binaries (when published): [Nextcore-Binaries](https://github.com/26x86/Nextcore-Binaries) ·
Docs: [26x86.github.io/26x86](https://26x86.github.io/26x86/) ·
Integration: [26x86/26x86](https://github.com/26x86/26x86)

## Modules

| Area | Repository | Owns |
| --- | --- | --- |
| **Patcher** | [26x86](https://github.com/26x86/26x86) | Guided workflow, OpenCore integration, EFI and root-patch preparation |
| **Boot core** | [Nextcore-Core](https://github.com/26x86/Nextcore-Core) | Configuration, public format codecs, and handoff contracts |
| **UEFI** | [Nextcore-EFI](https://github.com/26x86/Nextcore-EFI) | EFI application and controlled handoff probes |
| **Runtime** | [Nextcore-APLS](https://github.com/26x86/Nextcore-APLS) · [Nextcore-GPU](https://github.com/26x86/Nextcore-GPU) | Recovery diagnostics and GPU command execution |
| **Hardware translation** | [Nextcore-HAL](https://github.com/26x86/Nextcore-HAL) · [Nextcore-ISE](https://github.com/26x86/Nextcore-ISE) | Platform-table translation and freestanding ARM64e JIT runtime |
| **CLI** | [Nextcore-Tool](https://github.com/26x86/Nextcore-Tool) | Reproducible command-line orchestration |
| **Compatibility packages** | [OpenCorePkg](https://github.com/26x86/OpenCorePkg) · [MetallibSupportPkg](https://github.com/26x86/MetallibSupportPkg) · [PatcherSupportPkg](https://github.com/26x86/PatcherSupportPkg) | Upstream integration and patcher support |

Each NextCore module has its own Git history, pinned integration commit,
file-hash inventory, and CI gate. Module boundaries make layers easier to
inspect; they do not widen boot claims.

## Identity

Pink symbol with a dark wordmark. The image above is the master brand board:
primary lockup, scaled usage, and a dark-interface example. Do not crop,
recolor, or regenerate the board PNG for this profile.

---

<div align="center">

**NEXTCORE**

</div>
