# BenchmarkSCA-Go

> **Warning:** this repository intentionally pins vulnerable module versions for scanner
> evaluation. Do not build or execute it.

A public Go Modules SCA accuracy starter corpus for Vybscan. `ground-truth.json` is the independent
vulnerable/clean oracle. `go.sum` pins the resolved module graph so lockfile parsing and transitive
classification can be verified independently. The corpus remains intentionally small and is not a
claim of ecosystem-wide coverage.
