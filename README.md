---
tags: markdown cli makefile scripts
---

# [makedown]() - A Markdown powered Makefile alternative

`makedown` (aka Makefile + Markdown) is motivated by developers need to define
multiple scripts in one file next to their documentation, and have a handy way
to run them from terminal.

---

![](./docs/cast.mp4)

---

![](./docs/cast.gif)

---

- [Intro](#intro)
- [About](#about)
- [Installing and Updating](#installing-and-updating)
  - [Install & Update Script](#install--update-script)
    - [Additional Notes](#additional-notes)
    - [Troubleshooting on Linux](#troubleshooting-on-linux)
    - [Troubleshooting on macOS](#troubleshooting-on-macos)
    - [Ansible](#ansible)
  - [Verify Installation](#verify-installation)
  - [Important Notes](#important-notes)
  - [Git Install](#git-install)
  - [Manual Install](#manual-install)
  - [Manual Upgrade](#manual-upgrade)
- [Usage](#usage)
  - [Long-term Support](#long-term-support)
  - [Migrating Global Packages While Installing](#migrating-global-packages-while-installing)
  - [Default Global Packages From File While Installing](#default-global-packages-from-file-while-installing)
  - [io.js](#iojs)
  - [System Version of Node](#system-version-of-node)
  - [Listing Versions](#listing-versions)
  - [Setting Custom Colors](#setting-custom-colors)
    - [Persisting custom colors](#persisting-custom-colors)
    - [Suppressing colorized output](#suppressing-colorized-output)
  - [Restoring PATH](#restoring-path)
  - [Set default node version](#set-default-node-version)
  - [Use a mirror of node binaries](#use-a-mirror-of-node-binaries)
    - [Pass Authorization header to mirror](#pass-authorization-header-to-mirror)
  - [.nvmrc](#nvmrc)
  - [Deeper Shell Integration](#deeper-shell-integration)
    - [Calling `nvm use` automatically in a directory with a `.nvmrc` file](#calling-nvm-use-automatically-in-a-directory-with-a-nvmrc-file)
      - [bash](#bash)
      - [zsh](#zsh)
      - [fish](#fish)
- [Running Tests](#running-tests)
- [Environment variables](#environment-variables)
- [Bash Completion](#bash-completion)
  - [Usage](#usage-1)
- [Compatibility Issues](#compatibility-issues)
- [Installing nvm on Alpine Linux](#installing-nvm-on-alpine-linux)
  - [Alpine Linux 3.13+](#alpine-linux-313)
  - [Alpine Linux 3.5 - 3.12](#alpine-linux-35---312)
- [Uninstalling / Removal](#uninstalling--removal)
  - [Manual Uninstall](#manual-uninstall)
- [Docker For Development Environment](#docker-for-development-environment)
- [Problems](#problems)
- [macOS Troubleshooting](#macos-troubleshooting)
- [WSL Troubleshooting](#wsl-troubleshooting)
- [Maintainers](#maintainers)
- [Project Support](#project-support)
- [Enterprise Support](#enterprise-support)
- [License](#license)
- [Copyright notice](#copyright-notice)

---

`Makefile`s are great for this, but are lucking some of the
[`makedown`](https://github.com/tzador/makedown) features, such as syntax
highlighting, hierarchical scanning of .md files with embedded documentation.

There are also `package.json` scripts in `node.js` world, but users are forced
to write script commands in one line.

It is implemented in Python for portability reasons, since most Unix-like
systems already have a Python interpreter installed.

Here is [DEMO.md](./DEMO.md) file with examples of usage.

---

This is a fresh project still under active development.

Feel free to open and [issue](https://github.com/tzador/makedown/issues) or
[PR](https://github.com/tzador/makedown/pulls).

We also have have a [Discord](https://discord.gg/Gcr9H897zD) server for quick
discussions and sharing ideas or feedback.

---

## Key Features

- **Executable Markdown Scripting**: Use markdown files (.md) to organize
  commands and their documentation.
- **Multilingual Execution**: Supports `zsh`, `bash`, `javascript`, `python` and
  **infinitely** many more, using custom hashbangs.
- **Syntax Highlighting**: Leverages markdown code blocks for readability.

---

## Install

```bash
pip install makedown
```

## Use

Define commands in a `.md` file:

````markdown
# my_scripts.md

Here are a few examples of commands:

## [hello]() Prints "hello" using bash

```bash
echo "hello"
```

## [world]() Prints "world" using python

This is a more detailed description of the command.

```python
#!/usr/bin/env python

echo "world"
```
````

To run commands in a markdown file, execute `makedown` from the same directory
or any subdirectory:

```bash
makedown hello
```

A shorter version is also available:

```bash
m world
```

To see all the available commands with their short descriptions, use one of the
following:

```bash
makedown --help
```

or just run it without any arguments:

```bash
m
```

To get more details about a specific command, use:

```bash
makedown world --help
```

## Upgrade

```bash
pip install --upgrade makedown
```

## Uninstall

```bash
pip uninstall makedown
```
