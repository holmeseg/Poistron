---
title: Poistron
description: Positron and VS Code workspace setup, extension recommendations, and reusable Copilot prompts.
category: development
tags:
  - positron
  - visual-studio-code
  - workspace-configuration
  - github-copilot
---

# Poistron

Poistron contains workspace customization files for Positron and VS Code, including editor settings, a curated extension list, and reusable GitHub Copilot prompts. Use this repository to set up the workspace and keep its shared editor and assistant configuration in one place.

## Why Positron?

Positron is an open-source IDE designed for data science workflows. Its familiar VS Code-style environment brings code, data, and analysis tools together while allowing teams to evaluate it alongside their existing tools.

Explore the [Positron feature overview](https://positron.posit.co/features.html) for details.

### Key benefits

- **Integrated Git and version control:** The Source Control view provides visual diffs, staging, and merge-conflict workflows. Depending on the installed version and workflow, changes can be reviewed and staged in smaller units before committing.
- **AI-assisted development:** Positron supports AI-assisted coding workflows through available assistants and extensions. Features, model access, and the context an assistant can use depend on the configured provider, extensions, and account; external AI services may have separate licensing or usage costs.
- **R and Python workflows:** R and Python are supported as first-class languages, making it practical to work with both in the same IDE. Required language runtimes, packages, and project environments still need to be installed and configured.
- **Database exploration:** Data connections and interactive exploration can bring supported databases and data sources into the IDE. Available connectors and features depend on the Positron version and installed extensions.
- **Quarto and reproducible reporting:** Positron supports Quarto workflows for authoring and rendering reports, manuscripts, and presentations, with editing and preview capabilities depending on the installed tools.
- **Separate execution sessions:** Language and analysis sessions run separately from the editor interface. A session failure may leave the interface responsive, but it does not guarantee that unsaved work or running tasks will be preserved.

## Low-risk evaluation and transition

- **Coexistence:** Positron can be installed alongside RStudio and VS Code; trying it does not require removing those tools. Use the same R and Python installations where compatible, and verify each project's environment and dependencies.
- **No source-code migration required:** Existing `.R`, `.py`, and `.qmd` files can generally be opened directly. IDE-specific settings, extensions, and workflows may need adjustment.
- **Open-source IDE:** Positron is open source and does not require a paid IDE license. Optional extensions, AI providers, or hosted services may have their own terms, fees, or usage limits.
- **Pilot before switching:** Evaluate representative projects and workflows first, including Git operations, database connections, package environments, and report rendering, before making Positron the team's primary IDE.

## Install Positron

Download Positron from the [official download page](https://positron.posit.co/download.html). Choose the installer for your operating system and computer architecture; consult that page for current operating-system support and installer options.

### macOS

1. Select the macOS download that matches your Mac's processor (Apple silicon or Intel, when offered).
2. Open the downloaded disk image and follow the included installation instructions, typically dragging Positron into the Applications folder.
3. Open Positron from Applications. If macOS asks you to confirm that you want to open an app downloaded from the internet, follow your organization's security guidance.

### Windows

1. Select the Windows installer that matches your system, when architecture options are offered.
2. Run the downloaded installer and follow its prompts. If installation requires elevated permissions, follow your organization's software-installation policy.
3. Launch Positron from the Start menu.

### Language runtimes

Positron can be installed independently of R and Python, but you need the relevant language runtime to run projects in that language:

- **Python:** Use an actively supported Python version. Positron can offer to install Python using `uv`; alternatively, use a supported environment manager such as `venv`, `uv`, `pyenv`, or `conda`.
- **R:** Install R 4.2 or later if you plan to use R. On Windows, install Rtools as well only if your work requires building R packages from source.

See the official [Positron download and prerequisites guide](https://positron.posit.co/download.html) for current details.

## Repository contents

- [`.vscode/settings.json`](./.vscode/settings.json) — workspace color customizations, including Peacock theme colors.
- [`.github/prompts/`](./.github/prompts/) — reusable prompts for documenting files and recommending filenames. Invoke them in Copilot Chat with `/doc` and `/rename_file`.
- [`customization/extensions.md`](./customization/extensions.md) — extension names and IDs, with PowerShell instructions for writing the install list and installing extensions.
- [`customization/extensions.txt`](./customization/extensions.txt) — one VS Code extension ID per line.

## Set up the workspace

1. Open this repository as a folder in VS Code.
2. Install the recommended extensions by following the instructions in [`customization/extensions.md`](./customization/extensions.md).
3. Use the workspace settings and Copilot prompts as needed. The prompts are available from Copilot Chat when this workspace is open.

This repository contains configuration and documentation; no build or test commands are defined here.