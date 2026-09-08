<div align="center">
  <a href="https://github.com/26x86/26x86"><img src="https://raw.githubusercontent.com/26x86/26x86/main/resources/branding/nextcore-logo-256.png" alt="NextCore" width="120" /></a>
  <h1>NextCore · 26x86</h1>
  <p><strong>Public EFI boot engineering, from firmware to graphics.</strong></p>
  <p>macOS 26 Tahoe native HAL · macOS 27 Golden Gate AMD64 ↔ Apple Silicon HAL · Metal</p>
  <p><a href="https://github.com/26x86/26x86">Project</a> · <a href="https://github.com/26x86/26x86/blob/main/docs/NEXTCORE_CURRENT_CONTEXT.md">Current progress</a> · <a href="https://github.com/orgs/26x86/repositories">Repositories</a> · <a href="https://github.com/26x86/26x86/actions">CI</a></p>
</div>

NextCore is a clean-room EFI boot stack developed within 26x86. We are building
native platform support for Tahoe and the AMD64 ↔ Apple Silicon path for Golden
Gate, including guest Metal. These are active engineering goals; the complete
platform and graphics stack is not yet verified.

## What runs today

The [2026-09-08 source snapshot](https://github.com/26x86/26x86/tree/dcc90013109eac694ccbf997b1e44a7018480f78)
records each result at the layer actually exercised.

| Layer | Observed result | Remaining work |
| --- | --- | --- |
| NextCore EFI | GOP/text picker, keyboard selection and child launch in OVMF | Automatic OS volume discovery |
| Tahoe recovery | NextCore → original booter → XNU and userspace; readable, interactive Recovery menus in local QEMU/KVM | Independent KC-loader entry and complete native HAL |
| Golden Gate ARM64E | Public boot-argument codec and immutable KC host staging with full view readback | Physical placement, CPU/PAC/DT integration and original XNU entry |
| Graphics | Intel host Vulkan submission/readback; guest Metal probes built and a Tahoe Recovery probe executed | Guest probe reported no Metal device; **metal_verified=false** |

Host tests and emulator results do not establish physical-Mac support. Full
installation, the complete Golden Gate boot path and guest Metal remain open.
See the pinned [context](https://github.com/26x86/26x86/blob/dcc90013109eac694ccbf997b1e44a7018480f78/docs/NEXTCORE_CURRENT_CONTEXT.md)
and [validation record](https://github.com/26x86/26x86/blob/dcc90013109eac694ccbf997b1e44a7018480f78/nextcore/VALIDATION.md)
for the exact execution conditions and boundaries.
The [current development record](https://github.com/26x86/26x86/blob/main/docs/NEXTCORE_CURRENT_CONTEXT.md)
tracks later work; each released module retains its own immutable source-commit reference.

## Seven independently versioned modules

The `v0.1.1` snapshots use the source commit above. Tool `v0.1.2` includes a
[crate-local test-fixture correction](https://github.com/26x86/26x86/commit/045065700cbd037eaaa974faf957ba15cb628370).
Cross-module dependencies use fixed tags; inventories record the exported public
files. Package versions remain those of each source snapshot.

| Module | Responsibility | Fixed snapshot |
| --- | --- | --- |
| [Core](https://github.com/26x86/Nextcore-Core) | Configuration, public image/DT formats and architecture-specific preparation | [v0.1.1](https://github.com/26x86/Nextcore-Core/tree/26x86-Nextcore-Core-v0.1.1) |
| [EFI](https://github.com/26x86/Nextcore-EFI) | Firmware picker, platform services and bounded handoff | [v0.1.1](https://github.com/26x86/Nextcore-EFI/tree/26x86-Nextcore-EFI-v0.1.1) |
| [Tool](https://github.com/26x86/Nextcore-Tool) | CLI preparation and orchestration | [v0.1.2](https://github.com/26x86/Nextcore-Tool/tree/26x86-Nextcore-Tool-v0.1.2) |
| [HAL](https://github.com/26x86/Nextcore-HAL) | Public platform-table metadata | [v0.1.1](https://github.com/26x86/Nextcore-HAL/tree/26x86-Nextcore-HAL-v0.1.1) |
| [ISE](https://github.com/26x86/Nextcore-ISE) | Instruction and CPU feature policy | [v0.1.1](https://github.com/26x86/Nextcore-ISE/tree/26x86-Nextcore-ISE-v0.1.1) |
| [GPU](https://github.com/26x86/Nextcore-GPU) | Graphics contracts and optional host Vulkan backend | [v0.1.1](https://github.com/26x86/Nextcore-GPU/tree/26x86-Nextcore-GPU-v0.1.1) |
| [APLS](https://github.com/26x86/Nextcore-APLS) | ARM recovery orchestration and public guest interfaces | [v0.1.1](https://github.com/26x86/Nextcore-APLS/tree/26x86-Nextcore-APLS-v0.1.1) |

## Related projects and upstream integration

[26x86](https://github.com/26x86/26x86) also provides guided setup, OpenCore
integration, EFI preparation and diagnostics. [VenFire](https://github.com/26x86/VenFire)
and [VenFire-QEMU](https://github.com/26x86/VenFire-QEMU) hold the separate
emulation research track. Upstream integration and support packages remain in
[OpenCorePkg](https://github.com/26x86/OpenCorePkg),
[MetallibSupportPkg](https://github.com/26x86/MetallibSupportPkg) and
[PatcherSupportPkg](https://github.com/26x86/PatcherSupportPkg).

Public repositories contain independently authored source and public interfaces,
not Apple firmware, guest disks, extracted blobs or private research material.
