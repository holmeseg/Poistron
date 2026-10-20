---
title: VS Code Extensions
description: Curated VS Code extension names and IDs, with PowerShell commands to save and install the list.
category: development
tags:
  - visual-studio-code
  - extensions
  - extension-management
  - powershell
---

# VS Code Extensions

This document lists the curated VS Code extensions for this workspace, their command-line IDs, and a brief description of each extension.

| Extension name | Extension ID | Description |
| --- | --- | --- |
| Pastum | `atsyplenkov.pastum` | Converts copied text, HTML, or CSV tables into dataframe code for languages such as R and Python. |
| Spell Right | `ban.spellright` | Checks spelling in comments, strings, and supported document types. |
| Peacock | `johnpapa.vscode-peacock` | Customizes workspace colors to distinguish windows or projects. |
| Start Git Bash | `mccarter.start-git-bash` | Opens a Git Bash terminal from VS Code. |
| Rainbow CSV | `mechatroner.rainbow-csv` | Highlights CSV columns and provides tools for working with delimited data. |
| Python Debugger | `ms-python.debugpy` | Enables Python debugging with breakpoints and interactive inspection. |
| Python | `ms-python.python` | Adds Python language support, editing features, and interpreter selection. |
| Python Environments | `ms-python.vscode-python-envs` | Discovers and manages Python environments for projects. |
| Jupyter | `ms-toolsai.jupyter` | Supports editing and running Jupyter notebooks in VS Code. |
| Jupyter Keymap | `ms-toolsai.jupyter-keymap` | Adds familiar keyboard shortcuts for working with Jupyter notebooks. |
| Jupyter Notebook Renderers | `ms-toolsai.jupyter-renderers` | Renders rich notebook outputs such as plots and interactive visualizations. |
| Jupyter Cell Tags | `ms-toolsai.vscode-jupyter-cell-tags` | Adds support for tagging notebook cells. |
| Jupyter Slide Show | `ms-toolsai.vscode-jupyter-slideshow` | Helps create slideshows from tagged notebook cells. |
| R Debugger | `rdebugger.r-debugger` | Enables debugging of R code in VS Code. |
| R | `reditorsupport.r` | Adds R language support and common development features. |
| R Syntax | `reditorsupport.r-syntax` | Provides syntax highlighting for R code. |
| Rainbow Brackets | `tal7aouy.rainbow-bracket` | Uses distinct colors to help match nested brackets and delimiters. |
| Markdown All in One | `yzhang.markdown-all-in-one` | Adds Markdown editing shortcuts, previews, and formatting tools. |

## Prerequisites

- VS Code must be installed.
- PowerShell and the VS Code `code` command must be available.
- Run the commands from the repository root so the output file is created at the expected path.

## Create and install from `extensions.txt`

Run this PowerShell snippet to create `customization\extensions.txt` from the curated IDs above and install those extensions in VS Code:

```powershell
$extensions = @(
    'atsyplenkov.pastum'
    'ban.spellright'
    'johnpapa.vscode-peacock'
    'mccarter.start-git-bash'
    'mechatroner.rainbow-csv'
    'ms-python.debugpy'
    'ms-python.python'
    'ms-python.vscode-python-envs'
    'ms-toolsai.jupyter'
    'ms-toolsai.jupyter-keymap'
    'ms-toolsai.jupyter-renderers'
    'ms-toolsai.vscode-jupyter-cell-tags'
    'ms-toolsai.vscode-jupyter-slideshow'
    'rdebugger.r-debugger'
    'reditorsupport.r'
    'reditorsupport.r-syntax'
    'tal7aouy.rainbow-bracket'
    'yzhang.markdown-all-in-one'
)

$extensions | Set-Content -Path .\customization\extensions.txt
Get-Content .\customization\extensions.txt | ForEach-Object { code --install-extension $_ }
```

The first command writes one extension ID per line to the text file. The second reads those IDs and asks the VS Code command-line interface to install each extension. Run the snippet again whenever you want to recreate the file and install the listed extensions.

Keep the extension IDs in the PowerShell array aligned with the table above when updating this curated list. The generated `extensions.txt` contains only these entries; it is not a snapshot of all extensions currently installed. To print the IDs installed in the current VS Code environment, run:

```powershell
code --list-extensions
```