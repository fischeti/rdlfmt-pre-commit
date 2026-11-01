# rdlfmt-pre-commit

A [pre-commit](https://pre-commit.com) hook for
[rdlfmt](https://github.com/fischeti/rdlfmt), the SystemRDL formatter.

```yaml
repos:
  - repo: https://github.com/fischeti/rdlfmt-pre-commit
    rev: v0.4.2
    hooks:
      - id: rdlfmt
```

`rdlfmt` rewrites `.rdl` files in place. `rdlfmt-check` only reports the files
that are not formatted, for CI or anywhere the hook must not change files.

Each tag installs the rdlfmt release of the same version from PyPI, so `rev`
picks the formatter. Tags follow rdlfmt releases within a day.

## Staying up to date

`pre-commit autoupdate` moves `rev` to the latest tag. To have Dependabot open
the pull request instead, add to `.github/dependabot.yml`:

```yaml
version: 2
updates:
  - package-ecosystem: pre-commit
    directory: /
    schedule:
      interval: monthly
```

## License

Licensed under either of [Apache License, Version 2.0](LICENSE-APACHE) or
[MIT license](LICENSE-MIT) at your option.
