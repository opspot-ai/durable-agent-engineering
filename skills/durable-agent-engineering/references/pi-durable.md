# Pi Durable reference

This note points to public Pi Durable materials and related examples. It summarizes topics to inspect; it does not claim that any linked API is current or verified for a selected version. Check the selected runtime release, package manifests, source, and API contracts before coding.

## Public sources

- [Earendil's Pi Durable release and API examples](https://earendil.com/posts/pi-durable/): storage ownership, checkpointed model and tool tasks, replay policies, conversations and child-task ownership, durable documents, compaction, forks, extension changes, and client views. Check the project's current status and limitations.
- [The durable-pi implementation by IndyDevDan](https://github.com/disler/durable-pi): a device backend, shared SDK, browser hub, and terminal client. Inspect the source relevant to the capability being built; examples are not acceptance evidence for another product.
- [The source video](https://youtu.be/DNDYYHsypZg): the motivating example. Prefer current implementation and runtime source for behavior and limitations.

These links identify the external materials summarized here. No external runtime source is bundled in this repository.

## Adaptation notes

Reuse suitable runtime primitives and clients instead of recreating their harness. Keep product ownership and domain workflows in their own modules. A thin adapter for an external worker can help, but state its job-level recovery boundary rather than claiming its internal tool execution is checkpointed.

For a Pi-based design, preserve one process owner per storage. Use stable submission IDs and runtime-supported transactions, task ownership, documents, and replay declarations. Check fork semantics for shared state and pending operations. Pin compatible package versions using the upstream manifests instead of relying on a version noted here.

The examples distinguish durable checkpoints from exactly-once external effects. Treat start directories and bearer tokens according to the selected runtime's actual isolation and permission model; prose defaults are not enforcement. Inspect optional command guards and failure behavior before adopting them.

A useful validation slice is a local input that wakes its owner, produces a result, survives a runtime restart, and appears in two connected clients. Add the required real-source flow and focused project checks. Reading this reference does not authorize a fleet rollout, cloud purchase, third-party account, or production deployment.
