## Code Review Rules

Start with the intended change and review the diff in the context of affected callers, contracts, and system boundaries. Apply the checks that matter to the change and prioritize concrete user or operational impact.

- **Correctness and logic.** Check requirements, edge cases, state transitions, error paths, and data integrity. Trace how invalid or missing inputs propagate and how multiple operations interact.
- **Architecture and maintainability.** Check whether responsibilities belong in the changed component and whether dependencies flow in the intended direction. Flag coupling or duplicated business rules when they create a concrete risk of inconsistent behavior, break a contract, or make a required change unsafe.
- **Security and privacy.** Check changed trust boundaries, authentication and authorization, handling of untrusted input, secrets, dependency changes, and exposure of sensitive data through storage, logs, or external services. Base findings on reachable code and existing safeguards. Omit secret values from comments.
- **Compatibility and rollout.** Check existing callers, persisted data, supported platforms, configuration defaults, and deployment order. For contract or schema changes, consider mixed versions, migration safety, and rollback.
- **Reliability and operability.** Check concurrent execution, retries, timeouts, cleanup, partial failure, and recovery where relevant. Check whether consequential failures can be detected and diagnosed with the available logs or metrics.
- **Performance and resource use.** Check hot paths and realistic workloads for unbounded growth, unnecessary I/O, excessive allocation, or blocking work. Explain which workload makes the impact material.
- **User experience and accessibility.** For user-facing changes, check core flows and loading, empty, and error states. Check whether the change prevents users from completing a flow with supported input methods or assistive technology.
- **Tests and verification.** Check that tests exercise the behavior at risk through an appropriate entry point, including relevant failure or boundary cases. Flag missing coverage when it leaves a specific regression risk unguarded. Describe checks as run only when they were actually performed.

Report actionable issues that the PR introduces or makes reachable. For each finding, give its severity, the narrowest relevant location in the diff, the triggering condition, and the concrete impact. Base severity on impact and likelihood. Ground each finding in the code and avoid duplicates, stylistic preferences, and speculative risks.
