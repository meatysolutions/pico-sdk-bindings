# pico-sdk-bindings

[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/meatysolutions/pico-sdk-bindings/Build%20&%20Package?label=Build%20%26%20Package&logo=github)](https://github.com/meatysolutions/pico-sdk-bindings/actions)
![GitHub](https://img.shields.io/github/license/meatysolutions/pico-sdk-bindings?style=flat)

### Cross-platform, gap-free streaming from any Pico Technology oscilloscope

> **Note**: These are not official Pico Technology packages

These packages wrap all current Pico oscilloscope drivers in a high-level, common
API written in Rust. This API is compiled to native code and exposed to multiple
programming languages through simple C bindings.

## Rust

[![Crates.io](https://img.shields.io/crates/v/pico-sdk?color=dark-green&logo=rust)](https://crates.io/crates/pico-sdk)
[![docs.rs](https://docs.rs/pico-sdk/badge.svg)](https://docs.rs/pico-sdk/)

Check out the Rust libraries [in their own repository](https://github.com/meatysolutions/pico-sdk).

## .NET

[![Nuget](https://img.shields.io/nuget/v/PicoSDK?color=dark-green&logo=nuget)](https://www.nuget.org/packages/PicoSDK/)

Add the `PicoSDK` NuGet package:

```shell
dotnet add package PicoSDK
```

Check out the usage example in the [dotnet README](dotnet)

## Python

[![PyPI](https://img.shields.io/pypi/v/pico_sdk?color=dark-green&logo=pypi) ![PyPI - Python Version](https://img.shields.io/pypi/pyversions/pico_sdk)](https://pypi.org/project/pico-sdk/)

Install the `pico_sdk` package:

```shell
pip install pico_sdk
```

Check out the usage example in the [Python README](python)

## Node.js

[![npm](https://img.shields.io/npm/v/pico-sdk?color=dark-green&logo=npm) ![node-current](https://img.shields.io/node/v/pico-sdk?color=blue)](https://www.npmjs.com/package/pico-sdk)

Add the `pico-sdk` package:

```shell
npm i pico-sdk
```

Check out the usage example in the [node.js README](nodejs)

## Issues, Feature Requests and Contributions

Until a 1.0 release, the libraries in this repository are considered a work in
progress and do not follow semver semantics.

Please report any issues or feature requests in
[the issue tracker](https://github.com/meatysolutions/pico-sdk-bindings/issues). Pull
requests are welcome and encouraged!

## Building & Packaging

The Rust code will build and test on any platform via `cargo build` and
`cargo test`.

We pre-compile binaries for common platforms and architectures via GitHub
Actions.

- On Windows, macOS and Linux we run `node scripts/build.js` which compiles the
  Rust code to native libraries.
- For the final step we run `node scripts/bindings.js` which copies the native
  libraries to the correct directories and builds/packages for each language.
- On git tag creation, `node scripts/publish.js` publishes the packages to the
  respective package managers.

If you run the above steps manually, the resulting packages will only support
your current platform. The dotnet build currently fails if any native artifacts
are missing so you'll likely need to modify `PicoSDK.csproj` to build locally.
