<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Installation](#installation)
  - [Using go](#using-go)
  - [Using brew](#using-brew)
  - [Using release binary (pending to finish this)](#using-release-binary-pending-to-finish-this)
    - [Linux](#linux)
    - [Mac OSX](#mac-osx)
    - [Supported OS](#supported-os)
  - [Check version](#check-version)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Installation

## Using go

```bash
go install github.com/containerscrew/tftools
```
> **NOTE:** this installation mode is broken by using go:embed files. To be fixed 🛠️

## Using brew

```bash
brew tap containerscrew/tftools https://github.com/containerscrew/tftools
brew install tftools
```

## Using release binary (pending to finish this)

### Linux
```bash
TFTOOLS_CLI_VERSION=$(curl -s https://api.github.com/repos/containerscrew/tftools/releases/latest)
TFTOOLS_CLI_ARCH=amd64
if [ "$(uname -m)" = "aarch64" ]; then CLI_ARCH=arm64; fi
curl -L --fail --remote-name-all https://github.com/containerscrew/tftools/releases/download/${TFTOOLS_CLI_VERSION}/XXXXX-${TFTOOLS_CLI_ARCH}.tar.gz{,.sha256sum}
sha256sum --check xxxxxx-${CLI_ARCH}.tar.gz.sha256sum
sudo tar xzvfC xxxxxx-${CLI_ARCH}.tar.gz /usr/local/bin
rm xxxx-${CLI_ARCH}.tar.gz{,.sha256sum}
```

### Mac OSX

```bash
TFTOOLS_CLI_VERSION=$(curl -s https://api.github.com/repos/containerscrew/tftools/releases/latest)
TFTOOLS_CLI_ARCH=amd64
if [ "$(uname -m)" = "arm64" ]; then CLI_ARCH=arm64; fi
curl -L --fail --remote-name-all https://github.com/containerscrew/tftools/releases/download/${TFTOOLS_CLI_VERSION}/XXXXX-${TFTOOLS_CLI_ARCH}.tar.gz{,.sha256sum}
sha256sum --check xxxxxx-${CLI_ARCH}.tar.gz.sha256sum
sudo tar xzvfC xxxxxx-${CLI_ARCH}.tar.gz /usr/local/bin
rm xxxx-${CLI_ARCH}.tar.gz{,.sha256sum}
```

[Releases](https://github.com/containerscrew/tftools/releases)

### Supported OS

| OS        | ARM64 | AMD64 |
|-----------|:-----:|------:|
| Mac       |  √    |   √   |
| Linux     |  √    |   √   |

## Check version

```bash
tftools version
```