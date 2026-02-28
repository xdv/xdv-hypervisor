# Architecture
XDV Domain Hypervisor is structured in two layers:
1. Stable interface layer (src/hypervisor_interface.ds)
2. Implementation layer (src/hypervisor.ds)
Tests from the source sector are imported into src and can be mirrored into tests as independent suites over time.
