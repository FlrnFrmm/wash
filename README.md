[![Latest Release](https://img.shields.io/github/v/release/wasmcloud/wash?color=success&include_prereleases)](https://github.com/wasmCloud/wash/releases)
[![Rust Build](https://img.shields.io/github/workflow/status/wasmcloud/wash/Rust/main)](https://github.com/wasmCloud/wash/actions/workflows/rust.yml)
[![Rust Version](https://img.shields.io/badge/rustc-1.50.0-orange.svg)](https://blog.rust-lang.org/2015/12/10/Rust-1.5.html) 
[![Contributors](https://img.shields.io/github/contributors/wasmcloud/wash)](https://github.com/wasmCloud/wash/graphs/contributors)
[![Good first issues](https://img.shields.io/github/issues/wasmcloud/wash/good%20first%20issue?label=good%20first%20issues)](https://github.com/wasmCloud/wash/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)
```
                                     _                 _    _____ _          _ _ 
                                ____| |               | |  / ____| |        | | |
 __      ____ _ ___ _ __ ___  / ____| | ___  _   _  __| | | (___ | |__   ___| | |
 \ \ /\ / / _` / __| '_ ` _ \| |    | |/ _ \| | | |/ _` |  \___ \| '_ \ / _ \ | |
  \ V  V / (_| \__ \ | | | | | |____| | (_) | |_| | (_| |  ____) | | | |  __/ | |
   \_/\_/ \__,_|___/_| |_| |_|\_____|_|\___/ \__,_|\__,_| |_____/|_| |_|\___|_|_|
```
## Why wash
`wash` is a bundle of command line tools that, together, form a comprehensive CLI for [wasmcloud](https://github.com/wasmcloud/wasmcloud) development. Everything from generating signing keys to a fully interactive REPL environment is contained within the subcommands of `wash`. Our goal with `wash` is to encapsulate our tools into a single binary to make developing WebAssembly with wasmcloud painless and simple.

## Installing wash
### Cargo
```
cargo install wash-cli
```
### Linux (deb/rpm + apt)
```
# Debian / Ubuntu (deb)
curl -s https://packagecloud.io/install/repositories/wasmcloud/core/script.deb.sh | sudo bash
# Fedora (rpm)
curl -s https://packagecloud.io/install/repositories/wasmcloud/core/script.rpm.sh | sudo bash

sudo apt install wasmcloud wash
```
### MacOS (brew)
```
brew tap wasmcloud/wasmcloud
brew install wasmcloud wash
```
### NixOS
```
nix run github:wasmCloud/wash
```

## Using wash
`wash` has multiple subcommands, each specializing in one specific area of the wasmcloud development process.
### claims
Generate JWTs for actors, capability providers, accounts and operators. Sign actor modules with claims including capability IDs, expiration, and keys to verify identity. Inspect actor modules to view their claims.
### ctl
Interact directly with a wasmcloud [control-interface](https://github.com/wasmcloud/wasmcloud/tree/main/crates/control-interface), allowing you to imperatively schedule actors, providers and modify configurations of a wasmcloud host. Can be used to interact with local and remote control-interfaces.
### drain
Manage contents of the local wasmcloud cache. wasmcloud manages a local cache that will avoid redundant fetching of content when possible. `drain` allows you to manually clear that cache to ensure you're always pulling the latest versions of actors and providers that are hosted in remote OCI registries.
### keys
Generate ed25519 keys for securely signing and identifying wasmcloud entities (actors, providers, hosts). Read more about our decision to use ed25519 keys in our [ADR](https://wasmcloud.github.io/adr/0005-security-nkeys.html).
### par
Create, modify and inspect [provider archives](https://github.com/wasmcloud/provider-archive), a TAR format that contains a signed JWT and OS/Architecture specific binaries for native capability providers.
### reg
Push and Pull actors and capability providers to/from OCI compliant registries. Used extensively in our own CI/CD and in local development, where a local registry is used to store your development artifacts.
### up
Launch a fully interactive wasmcloud REPL environment, where all of the above subcommands are available to you. `up` provides you with a wasmcloud host, so you can get started running actors and providers without ever touching a line of code.

## Contributing to wash
If you have any feature suggestions, find any bugs, or otherwise have a question, please submit an issue [here](https://github.com/wasmcloud/wash/issues/new/choose). Forking & submitting Pull Requests are welcome, and the [good first issue](https://github.com/wasmcloud/wash/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22) label is a great way to find a place to start if you're looking to contribute.
