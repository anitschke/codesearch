# Code Search

Code Search is a tool for indexing and then performing regular expression
searches over large bodies of source code. It is a set of command-line programs
written in Go.

This is a fork of Russ Cox's https://github.com/google/codesearch.

## What is different about this fork?

- Add GitHub Actions CI to run Go tests on PRs and master. ([#2](https://github.com/anitschke/codesearch/pull/2))
- Remove `cmd/` and `lib/` directories — this fork is consumed as a library only. ([#3](https://github.com/anitschke/codesearch/pull/3))
