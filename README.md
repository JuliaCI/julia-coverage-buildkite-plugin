# julia-codecov-plugin

This plugin provides a convenient way to submit coverage reports to
[Codecov](https://codecov.io/) using
[Coverage.jl](https://github.com/JuliaCI/Coverage.jl).


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
