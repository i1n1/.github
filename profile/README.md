<div align="center">
  <a href="https://github.com/26x86/26x86"><img src="https://raw.githubusercontent.com/26x86/26x86/main/resources/branding/26x86-logo-256.png" alt="26x86" width="120" /></a>
  <h1>26x86</h1>
  <p><strong>macOS 26 support for x86-based Macintosh hardware.</strong></p>
  <p>OpenCore integration · clean-room boot engineering · evidence-first compatibility tooling</p>
  <p><a href="https://github.com/26x86/26x86">Explore 26x86</a> · <a href="https://github.com/orgs/26x86/repositories">All repositories</a> · <a href="https://github.com/26x86/26x86/actions">CI</a></p>
</div>

## What we build

26x86 keeps the patcher, boot contracts, emulator research, and compatibility
packages independently reviewable. Modules publish source inventories, fixed
tags, and CI checks so a result is traceable to the layer that produced it.

| Track | Repositories | Focus |
| --- | --- | --- |
| **Patcher** | [26x86](https://github.com/26x86/26x86) | Guided setup, OpenCore integration, EFI preparation, diagnostics |
| **Nextcore boot stack** | [Core](https://github.com/26x86/Nextcore-Core) · [EFI](https://github.com/26x86/Nextcore-EFI) · [Tool](https://github.com/26x86/Nextcore-Tool) | Public boot configuration, UEFI probes, and reproducible CLI control |
| **Nextcore runtime** | [APLS](https://github.com/26x86/Nextcore-APLS) · [GPU](https://github.com/26x86/Nextcore-GPU) · [HAL](https://github.com/26x86/Nextcore-HAL) · [ISE](https://github.com/26x86/Nextcore-ISE) | Recovery orchestration, platform translation, graphics, and instruction policy |
| **Emulation research** | [VenFire](https://github.com/26x86/VenFire) · [VenFire-QEMU](https://github.com/26x86/VenFire-QEMU) | VMApple/TCG contracts, storage integrity, and recovery evidence |
| **Support packages** | [OpenCorePkg](https://github.com/26x86/OpenCorePkg) · [MetallibSupportPkg](https://github.com/26x86/MetallibSupportPkg) · [PatcherSupportPkg](https://github.com/26x86/PatcherSupportPkg) | Upstream integration and compatibility support |

## Evidence, not optimism

- A static check, emulator probe, or synthetic guest PASS is not a physical-Mac
  or macOS boot claim.
- `macos_boot_verified` requires target-matching firmware, XNU, and userspace
  evidence. Each is recorded as a separate acceptance gate.
- Public repositories include no Apple firmware, guest disks, extracted blobs,
  or private reverse-engineering material.

Start with [the 26x86 project](https://github.com/26x86/26x86), where the
current validation boundary and user-facing setup paths are documented.
