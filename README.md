# XDV Domain Hypervisor
Version: 0.1.1
Status: active-split
Language: Dust Programming Language (DPL)

## Specification Alignment
- Primary: XDV-014 (Domain Hypervisor)
- Reference: XDV-083 (Domain Hypervisor Reference)

## Purpose
`xdv-hypervisor` provides deterministic Virtual Hybrid Machine (VHM) orchestration behavior for K/Q/Phi domain virtualization.

## Scope Implemented in 0.1.1
- VHM lifecycle transition checks (`requested -> validated -> active -> paused/terminated -> released`).
- Nested virtualization constraint checks (depth/quota/capability gating).
- Resource table ownership encoding and cross-VHM isolation validation.
- Resource conservation validation against physical totals.
- Snapshot policy checks for K/Q/Phi raw-state handling.
- Migration policy checks for Q/Phi live migration constraints.

## Public Surface
Core implementation: `src/hypervisor.ds`

Key APIs:
- `vhm_lifecycle_transition(...)`
- `validate_nested_constraints(...)`
- `create_nested_virtual_machine(...)`
- `build_resource_table_entry(...)`
- `validate_resource_table_isolation(...)`
- `validate_resource_conservation(...)`
- `snapshot_policy_check(...)`
- `migration_policy_check(...)`
- `check_q_migration_policy(...)`
- `check_phi_migration_policy(...)`

Version APIs:
- `xdv_hypervisor_interface_version_major/minor/patch`
- `xdv_hypervisor_lifecycle_api_version`
- `xdv_hypervisor_isolation_api_version`
- `xdv_hypervisor_policy_api_version`

## Build
`cargo run --manifest-path dust/Cargo.toml -- check xdv-hypervisor/src`

## Integration Notes
- `xdv-kernel` compatibility is preserved via existing `xdv_hypervisor_interface_version_*` exports.
- Existing wrapper APIs (`create_virtual_machine`, `configure_vcpus`, `start_virtual_machine`, etc.) remain available.
