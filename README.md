# XDV Domain Hypervisor
Version: 0.1.0
Status: active-split
Language: Dust Programming Language (DPL)
## Specification Alignment
Primary specification: XDV-014 in xdv-spec.
## Purpose
Standalone Domain Hypervisor project for virtual hybrid machine lifecycle and isolation controls.
This repository was split from xdv-kernel/sector/xdv_hypervisor into a standalone project so interfaces can evolve independently under stable versioning.
## Split Provenance
- Source sector: xdv-kernel/sector/xdv_hypervisor
- Imported Dust modules: src/hypervisor.ds and src/hypervisor_tests.ds
- Import model: source-copy split (non-destructive to existing kernel sector)
## Stable Interface Contract
This project defines a stable external interface boundary in:
- src/hypervisor_interface.ds
- docs/interface_contract.md
Compatibility model:
- Semantic interface versioning (major/minor/patch)
- Additive changes are minor releases
- Breaking signature/semantic changes are major releases
- Deprecated APIs remain one minor cycle before removal
## Repository Layout
- src/ : implementation and interface surfaces
- tests/ : standalone tests and integration placeholders
- docs/ : architecture and interface docs
- State.toml : workspace manifest
- changelog.md : release notes
- LICENSE : copied from xdv-os/LICENSE
## Public Surface
- Forge module: XdvHypervisor
- Primary implementation: src/hypervisor.ds
- Stable interface profile: src/hypervisor_interface.ds
## Dependencies
Planned dependencies:
- xdv-dal, xdv-cds, xdv-umf, xdv-kernel
- Dust toolchain and runtime packages required by integration profile
## Build
dust check xdv-hypervisor/src
## Test
dust test xdv-hypervisor/tests
## Integration Notes
- Kernel integration should consume this project via explicit version pinning.
- xdv-os integration should use release tags from this repo, not kernel-internal paths.
- API changes must update docs/interface_contract.md and changelog.md in the same change set.
