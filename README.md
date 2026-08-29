# BenchmarkSCA-Go

> **Warning:** this repository intentionally pins vulnerable module versions for scanner
> evaluation. Do not build or execute it.

A public, reproducible Go Modules SCA accuracy corpus. Every module in the resolved `go.sum`
graph is labelled in `ground-truth.json`; there are no unlabelled modules hidden from the
precision or recall denominators.

## Current scorecard

| Modules | Expected findings | Expected clean | Precision | Recall | F1 | Coverage |
|---:|---:|---:|---:|---:|---:|---:|
| 26 | 4 | 22 | 100.00% | 100.00% | 100.00% | 100.00% |

The score is pinned to staging scan commit `ff1187b` and analyzer `3db6559658cd`.

## Coverage and reproducibility

- Four direct modules and twenty-two resolved lockfile modules.
- Vulnerable direct and transitive modules plus clean precision controls.
- Every exact label is rechecked against OSV in CI.
- CI fails on a false positive, false negative, unscanned oracle case, unlabelled scanned module,
  stale advisory, or score below 100%.

Run locally:

```bash
node scripts/verify-oracle.mjs
node scripts/score.mjs
```

The score applies to this version-pinned corpus; it is not an ecosystem-wide prevalence claim.
