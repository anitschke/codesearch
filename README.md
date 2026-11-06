# Code Search

Code Search is a tool for indexing and then performing regular expression
searches over large bodies of source code. It is a set of command-line programs
written in Go.

This is a fork of Russ Cox's https://github.com/google/codesearch.

## What is different about this fork?

- Add GitHub Actions CI to run Go tests on PRs and master. ([#2](https://github.com/anitschke/codesearch/pull/2))
- Remove `cmd/` and `lib/` directories — this fork is consumed as a library only. ([#3](https://github.com/anitschke/codesearch/pull/3))
- Add versioning documentation and update module path to `github.com/anitschke/codesearch`. ([#4](https://github.com/anitschke/codesearch/pull/4))
- Add configurable index limits (`maxFileLen`, `maxLineLen`, `maxTextTrigrams`) via functional options on `Create`. ([#5](https://github.com/anitschke/codesearch/pull/5))
- Add `WithZipExtensions` option to configure which file extensions are treated as zip archives for indexing (e.g., `.slx`, `.jar`). ([#6](https://github.com/anitschke/codesearch/pull/6))
- Close the index file and temporary files when `IndexWriter.Flush` finishes, and unmap the temporary posting file, so they no longer stay open (on Windows, open files can't be deleted and keep their volume from being dismounted). ([#7](https://github.com/anitschke/codesearch/pull/7))
- Merge upstream [`74a12a9`](https://github.com/google/codesearch/commit/74a12a911a79b901d1158c48d011b2da1b090fc9), a small `sortPost` performance optimization that avoids copying its counting array. ([#8](https://github.com/anitschke/codesearch/pull/8))

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
