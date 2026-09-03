# bd-cli-releases

Public distribution point for prebuilt binaries of `bd`, bitdrift's command-line tool. This repository
contains no source code — it only hosts release artifacts. See [GitHub Releases](../../releases) for all
versions.

## Install via Homebrew (recommended)

```sh
brew tap bitdriftlabs/bd
brew install bd
```

## Manual download

Each [release](../../releases/latest) publishes a `checksums.txt` plus two kinds of assets per platform:

- `bd-<platform>` — a standalone binary
- `bd-cli-<platform>.tar.gz` — the same binary packaged as a tarball

Supported platforms:

| Platform | Binary asset | Tarball asset |
|---|---|---|
| Linux x86_64 | `bd-linux-x86_64` | `bd-cli-linux-x86_64.tar.gz` |
| Linux arm64 | `bd-linux-arm64` | `bd-cli-linux-arm64.tar.gz` |
| macOS x86_64 (Intel) | `bd-macos-x86_64` | `bd-cli-mac-x86_64.tar.gz` |
| macOS arm64 (Apple Silicon) | `bd-macos-arm64` | `bd-cli-mac-arm64.tar.gz` |
| macOS universal | `bd-macos-universal` | `bd-cli-mac-universal-apple-darwin.tar.gz` |

Example, downloading the macOS arm64 binary directly:

```sh
curl -fsSL -o bd \
  https://github.com/bitdriftlabs/bd-cli-releases/releases/latest/download/bd-macos-arm64
chmod +x bd
sudo mv bd /usr/local/bin/bd
```

### Verifying a download

```sh
curl -fsSL -o checksums.txt \
  https://github.com/bitdriftlabs/bd-cli-releases/releases/latest/download/checksums.txt
shasum -a 256 -c checksums.txt --ignore-missing
```

## Usage

Once installed, authenticate and start using the CLI:

```sh
bd auth
bd tail ios
```

Run `bd help` (or `bd <command> --help`) for full usage docs, including config file locations, JSON
output, chart/connector commands, and shell completions.

## Versioning

Releases in this repo are tagged to match the corresponding CLI release (e.g. `v0.2.27`) and are
republished automatically.
