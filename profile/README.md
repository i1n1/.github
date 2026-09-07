# 26x86

Better macOS system support for x86-based Macintosh-class hardware — an
OpenCore-style module family: one core package, focused companion modules,
explicit contracts, and evidence-gated claims.

## Modules

| Repository | Role |
| --- | --- |
| [26x86](https://github.com/26x86/26x86) | Core: OpenCore integration, EFI preOS/JIT, native host control plane, integration contracts |
| [VenFire](https://github.com/26x86/VenFire) | ARM64 VMApple/TCG conformance, storage integrity, and recovery policy tooling |
| [VenFire-QEMU](https://github.com/26x86/VenFire-QEMU) | Reproducible QEMU VMApple TCG/headless patch series pinned to an upstream QEMU commit |
| [OpenCorePkg](https://github.com/26x86/OpenCorePkg) | OpenCore bootloader fork used by the core package |
| [MetallibSupportPkg](https://github.com/26x86/MetallibSupportPkg) | Metal library patching utilities |
| [PatcherSupportPkg](https://github.com/26x86/PatcherSupportPkg) | Patcher support package |

## Claim discipline

- A synthetic guest PASS or a QEMU capability probe is **not** a macOS boot
  result.
- `macos_boot_verified` requires target-matching XNU and userspace evidence
  from caller-supplied signed inputs; repositories ship no Apple firmware or
  guest disks.
- Every module declares its contract in `repository.json` and its CI gates;
  release tags are minted only per the declared release policy.
