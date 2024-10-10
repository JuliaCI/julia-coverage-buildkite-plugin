# julia-coverage-buildkite-plugin

[![Build status](https://badge.buildkite.com/4865b0c4f907497e3e7dd06013baf92d1bd999ed340d7bca29.svg?branch=main)](https://buildkite.com/julialang/julia-coverage-buildkite-plugin)
[![codecov](https://codecov.io/github/JuliaCI/julia-coverage-buildkite-plugin/branch/main/graph/badge.svg?token=W2SRYBH46V)](https://codecov.io/github/JuliaCI/julia-coverage-buildkite-plugin)

This plugin provides a convenient way to submit coverage reports to
[Codecov](https://codecov.io/) using
[CoverageTools.jl](https://github.com/JuliaCI/CoverageTools.jl) and the Codecov CLI.


## Example

```yaml
steps:
  - label: ":julia: Run tests and submit coverage"
    plugins:
      - JuliaCI/julia#v1:
          version: "1.6"
      - JuliaCI/julia-test#v1: ~
      - JuliaCI/julia-coverage#v1: ~
```

Note that Codecov does not support tokenless submission from Buildkite, so you
will need to specify your `CODECOV_TOKEN`, e.g., by using the
[cryptic](https://github.com/staticfloat/cryptic-buildkite-plugin) buildkite
plugin.


## Options

* `dirs`: A list of directories to process coverage for. Defaults to `src`.
