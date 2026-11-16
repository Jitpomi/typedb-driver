# Maintained TypeDB 3.13 transport integration

Base: upstream 3.13.6, with Rust source verified identical to the registry package before migration. Preserve all upstream source, history, licenses and protocol behavior.

Migrate Tonic and Prost to 0.14 and use the public Body and interceptor response-body types. Pin the matching protocol generation branch built from unchanged 3.13.4 proto definitions. Preserve native TLS roots, certificate verification, authentication injection, transactions, deadlines and query semantics. Remove the unused normal async-std dependency, as in the existing registry package; no source uses it.

This is explicitly a JITPOMI-maintained compatibility branch, not an upstream release. Consumers pin the reviewed commit. Validate with the driver library tests, protocol TLS tests and the real DogRS/Business TypeDB authentication, tenant policy, rollback and conflict suites. Replace the source pin when an equivalent maintained upstream release passes those same checks. No advisory ignores, TLS weakening or authorization changes are introduced.
