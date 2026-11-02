
# EdgeForge — Embedded Linux Data Gateway

## Overview

EdgeForge is an embedded Linux project targeting the STM32MP157DK. It demonstrates custom Linux image generation, kernel driver development, and userspace networking applications.

The system receives TCP/IP data and stores it through a custom Linux character driver implementing a circular buffer.

## Architecture

See the [Project Overview Wiki](WIKI_PROJECT_OVERVIEW_URL).

## Repository Structure

- `layers/`: Custom Yocto layers.
- `conf/`: Build configuration templates.
- `scripts/`: Environment setup and build scripts.
- `docs/`: Technical documentation.

External dependencies, including the STM32MP1 BSP and application/kernel source repositories, are maintained separately.

## Build Instructions

See [Build and Deployment Documentation](WIKI_BUILD_URL).

## Hardware

- STM32MP157DK
- Cortex-A7 running Embedded Linux
- Ethernet connectivity

## Project Management

- [GitHub Project Board](GITHUB_PROJECT_URL)
- [Project Overview](WIKI_PROJECT_OVERVIEW_URL)
- [Project Schedule](WIKI_SCHEDULE_URL)

## Development Status

Currently in Sprint 1: Yocto image and hardware bring-up.

## License

MIT
