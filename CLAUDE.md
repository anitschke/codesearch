# codesearch fork

This is a fork of Russ Cox's https://github.com/google/codesearch maintained at
https://github.com/anitschke/codesearch.

## Tracking changes

When making changes to this fork, add a bullet point to the "What is different
about this fork?" section in `README.md`. Each bullet should be a short (1-2
sentence) description of the change followed by a link to the PR where the
change was made.

## Build and test

```bash
go test ./...
```

## Project structure

- `index/` — Trigram index creation (`write.go`, `merge.go`) and reading (`read.go`)
- `regexp/` — Regexp-to-trigram query compiler
- `cmd/` — CLI tools (cindex, csearch, cgrep, csweb)
