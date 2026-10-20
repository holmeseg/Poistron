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

This document lists the curated VS Code extensions for this workspace. The table pairs each extension's display name with the ID used by the VS Code command-line interface.

| Extension name | Extension ID |
| --- | --- |
| Pastum | `atsyplenkov.pastum` |
| Spell Right | `ban.spellright` |
| Peacock | `johnpapa.vscode-peacock` |
| Start Git Bash | `mccarter.start-git-bash` |
| Rainbow CSV | `mechatroner.rainbow-csv` |
| Python Debugger | `ms-python.debugpy` |
| Python | `ms-python.python` |
| Python Environments | `ms-python.vscode-python-envs` |
| Jupyter | `ms-toolsai.jupyter` |
| Jupyter Keymap | `ms-toolsai.jupyter-keymap` |
| Jupyter Notebook Renderers | `ms-toolsai.jupyter-renderers` |
| Jupyter Cell Tags | `ms-toolsai.vscode-jupyter-cell-tags` |
| Jupyter Slide Show | `ms-toolsai.vscode-jupyter-slideshow` |
| R Debugger | `rdebugger.r-debugger` |
| R | `reditorsupport.r` |
| R Syntax | `reditorsupport.r-syntax` |
| Rainbow Brackets | `tal7aouy.rainbow-bracket` |
| Markdown All in One | `yzhang.markdown-all-in-one` |

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