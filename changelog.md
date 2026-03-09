# Changelog

## 0.1.1 - XDV-014 / XDV-083 Hypervisor Contract Milestone
- Replaced placeholder `src/hypervisor.ds` logic with deterministic hypervisor control paths.
- Added VHM lifecycle transition enforcement and nested virtualization constraints.
- Added resource table ownership encoding and isolation validation APIs.
- Added resource conservation checks.
- Added snapshot policy checks for K/Q/Phi state handling.
- Added migration policy checks for Q/Phi live migration constraints.
- Added concrete tests in `src/hypervisor_tests.ds` for lifecycle, nested constraints, isolation, and policy behavior.
- Added namespaced version-surface APIs in `src/hypervisor_interface.ds`.

## 0.1.0 - Sector Split Baseline
- Created standalone project from `xdv-kernel/sector/xdv_hypervisor`.
- Copied source module and tests into `src/`.
- Added stable interface file: `src/hypervisor_interface.ds`.
- Added initial docs and interface contract.
- Added LICENSE copied from `xdv-os/LICENSE`.
