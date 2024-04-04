# [AMDmi3](https://github.com/AMDmi3)'s omnilinter rules

[![CI](https://github.com/AMDmi3/omnilinter-rules-amdmi3/actions/workflows/ci.yml/badge.svg)](https://github.com/AMDmi3/omnilinter-rules-amdmi3/actions/workflows/ci.yml)

Feel free to use as example and as a base for your ruleset.

List of checks and considerations (not comprehensive):

## Ruleset summary

### projects.conf - ruleset for my F/OSS projects

- General
  - Require README
  - Require LICENSE
  - Require CI pipeline
  - Require CI badge in README
  - Migrate off coveralls as a coverage service
  - Migrate off travis as a CI service
- General source files
  - Require license info on SPDX format
  - Detect trailing whitespace
  - Detect commit markers
  - Highlight XXX, TODO, FIXME items
- Github actions
  - Update used actions to latest versions
  - Specify codecov token (is now required)
  - Enable dependabot for rust projects
  - Update container versions (ubuntu-latest or ubuntu-rolling if custom image is used)
- Rust
  - Highlight `[ignore]`d tests
  - Require documentation
- Cargo
  - Require some manifest fields
- Makefiles [^1]
  - Require `all` target to be defined
  - Require tabs indentation
  - Make sure compiler and flags are overridable
  - Make sure install is relative to DESTDIR
- CMake
  - Use lowercase commands
  - Always use GNUInstallDirs paths when installing
  - Specify `VERSION` and `LANGUAGES` in `project()`
  - Set C++ standard with `CMAKE_CXX_STANDARD`, not flags
  - Update to latest C++ standard
  - Update to latest CMake
  - Require linking third party libraries through targets
- C++
  - Convert include guards to `#pragma once`
- Python
  - Require `pyproject.toml`
  - Type annotation modernizations

[^1]: I dont really write these, so rules are given as example or for
third party code checking.

### freebsd-ports.conf - ruleset for FreeBSD ports

- Require `LICENSE`, `LICENSE_FILE`
- Enforce consistent install target names `do-install*` vs. `post-intstall*`
- Move distfiles off my mirror
- Add GitHub and PyPI `WWW`'s
- Convert from `USES=pytest` to `USE_PYTHON=pytest`
- Silent/verbose commands consistency
- Enforce patch upstreaming
- Highlight deprecated ports

## Author

* [Dmitry Marakasov](https://github.com/AMDmi3) <amdmi3@amdmi3.ru>

## License

* [CC0](LICENSE)
