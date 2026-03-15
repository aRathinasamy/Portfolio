# Learnings

> Notes, experiments, and write-ups from things I've studied, built, or broken. Treat this as a public second brain.

---

## React Performance Patterns

**Frontend · Updated Jan 2025**

Deep-dive into memoization strategies (`useMemo`, `useCallback`, `React.memo`), concurrent rendering with `useTransition`, and lazy loading with `Suspense`.

Key takeaways:
- Premature optimization hurts readability more than it helps perf
- Profiler-first approach: measure before you memoize
- Server Components in Next.js 14+ change the calculus significantly

[Read notes →](./react-performance.md)

---

## PostgreSQL Indexing Deep-Dive

**Backend · Updated Dec 2024**

Research on B-tree vs GIN indexes, understanding the query planner, and practical `EXPLAIN ANALYZE` walkthroughs on real datasets.

Key takeaways:
- Partial indexes are underused and extremely effective
- Index bloat is a real production concern
- BRIN indexes shine on time-series / append-only tables

[Read notes →](./postgres-indexing.md)

---

## Docker & Kubernetes Basics

**DevOps · Updated Nov 2024**

Step-by-step notes on containerization patterns, Kubernetes resource types, and production deployment strategies with Helm charts.

Key takeaways:
- Multi-stage builds dramatically reduce image size
- Resource limits and liveness probes are not optional in prod
- Helm makes repeatable deployments manageable

[Read notes →](./docker-k8s.md)

---

## Web Security Fundamentals

**Security · Updated Oct 2024**

OWASP Top 10 study notes covering XSS, CSRF, SQL injection, IDOR, and JWT best practices with practical mitigation examples.

Key takeaways:
- Content Security Policy headers eliminate most XSS risk
- Parameterized queries, always — no exceptions
- Signed, short-lived JWTs + refresh token rotation is the gold standard

[Read notes →](./web-security.md)
