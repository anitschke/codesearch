# Code Search

Code Search is a tool for indexing and then performing regular expression
searches over large bodies of source code. It is a set of command-line programs
written in Go.

This is a fork of Russ Cox's https://github.com/google/codesearch.

## What is different about this fork?

- Add GitHub Actions CI to run Go tests on PRs and master. ([#2](https://github.com/anitschke/codesearch/pull/2))
- Remove `cmd/` and `lib/` directories — this fork is consumed as a library only. ([#3](https://github.com/anitschke/codesearch/pull/3))
- Add versioning documentation and update module path to `github.com/anitschke/codesearch`. ([#4](https://github.com/anitschke/codesearch/pull/4))

## Versioning

This project follows [Semantic Versioning](https://semver.org/).

### Cutting a release

1. Ensure `master` is in the state you want to release.
2. Tag and push:
   ```bash
   VERSION=v1.2.3; git tag $VERSION && git push origin $VERSION
   ```

### Depending on this fork

```go
// go.mod
require github.com/anitschke/codesearch v1.2.3
```
