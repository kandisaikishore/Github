# Scalability baseline

Scale this project according to measured demand and its actual stack. Avoid unnecessary distributed infrastructure.

## Priorities
- Profile representative workflows and identify bottlenecks before optimizing or adding replicas.
- Bound request/input size, concurrent work, retries, and external provider timeouts.
- Paginate large collections and optimize measured database or vector-search hot paths.
- Keep service instances stateless where practical; externalize shared state before horizontal scaling.
- Add request correlation IDs, structured logs, metrics, health/readiness checks, and graceful shutdown for hosted services.
- Keep secrets in deployment configuration and protect user data in logs and diagnostic output.
- Add automated build, unit, integration, dependency/security, and smoke checks appropriate to the stack.

## Load validation
Test normal, peak, and burst traffic with representative data. Track throughput, p95/p99 latency, error rates, CPU/memory, provider quotas/cost, database wait time, and queue lag where relevant.

## Release gates
- [ ] Dependency outages and provider rate limits are handled predictably.
- [ ] Retries are bounded and state-changing tasks are idempotent where needed.
- [ ] Rollback and data backup/restore are documented where persistence exists.
- [ ] Capacity assumptions and actual load-test results are recorded.

This checklist is not evidence of completed load testing or production scaling.