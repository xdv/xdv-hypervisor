# Interface Contract
Project: XDV Domain Hypervisor
Specification: XDV-014 / XDV-083
Forge: XdvHypervisor

## Versioning
- Interface version: 0.1.0
- Lifecycle API version: 1
- Isolation API version: 1
- Policy API version: 1
- Stability tier: frozen_normative

## Contract Rules
- VHM lifecycle transitions must be deterministic and capability-scoped.
- Nested virtualization checks must enforce depth/quota constraints.
- Resource table ownership and attachment must be VHM-isolated.
- Snapshot and migration policy checks must be explicit and deterministic.

## Public Files
- `src/hypervisor.ds`
- `src/hypervisor_interface.ds`

## Key Public APIs
- `vhm_lifecycle_transition(...)`
- `validate_nested_constraints(...)`
- `create_nested_virtual_machine(...)`
- `validate_resource_table_isolation(...)`
- `validate_resource_conservation(...)`
- `snapshot_policy_check(...)`
- `migration_policy_check(...)`

## Stable Version APIs
- `xdv_hypervisor_interface_version_major()`
- `xdv_hypervisor_interface_version_minor()`
- `xdv_hypervisor_interface_version_patch()`
- `xdv_hypervisor_lifecycle_api_version()`
- `xdv_hypervisor_isolation_api_version()`
- `xdv_hypervisor_policy_api_version()`
