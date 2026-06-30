# Build N60 Pro 512M

This repository builds an OpenWrt image for the Netcore N60 Pro `512MB SPI-NAND` variant through GitHub Actions.

## Overview

- The build is based on the official `openwrt/openwrt` repository at `v25.12.5`
- A separate `512ROM` device variant is added on top of the officially supported `Netcore N60 Pro`
- The `512M` idea was inspired by the `moshanghuakai01/netcore-n60-pro` repository and its `dailook`-based approach, but this repository reimplements it for the OpenWrt mainline `filogic` tree
- The current implementation uses a minimal patch set and avoids unrelated package changes

## Build Flow

- GitHub Actions workflow: [.github/workflows/build-openwrt-n60-pro-512rom.yml](.github/workflows/build-openwrt-n60-pro-512rom.yml)
- Automatic trigger: pushes to `main` or `master`
- Manual trigger: run `build-openwrt-n60-pro-512rom` from the Actions page

## Key Files

- [configs/netcore_n60-pro-512rom.config](configs/netcore_n60-pro-512rom.config) - build config for the 512ROM variant
- [patches/0001-mediatek-filogic-add-netcore-n60-pro-512rom.patch](patches/0001-mediatek-filogic-add-netcore-n60-pro-512rom.patch) - device support patch for mainline OpenWrt

## Output

Build artifacts are uploaded as GitHub Actions artifacts.
