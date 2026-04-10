# Architecture

`xdv-hypervisor` is organized as:
1. Stable interface surface (`src/hypervisor_interface.ds`)
2. Deterministic hypervisor core (`src/hypervisor.ds`)

## Core Enforcement Blocks
- Lifecycle block:
  - VHM state validation and deterministic transition rules.
- Nested virtualization block:
  - depth, quota, and capability constraints for nested VHMs.
- Isolation block:
  - resource table ownership/attachment checks.
- Policy block:
  - snapshot policy checks,
  - migration policy checks for K/Q/Phi paths.

## Determinism
No random arbitration is used.
Lifecycle, isolation, and policy decisions are deterministic for identical inputs.
