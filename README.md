# Cursor IDE Setup — Tool Installation & Configuration Log

A detailed walkthrough of setting up Cursor IDE with the Claude Code and Codex AI extensions, connecting to GitHub, and documenting the full process.

---

## Table of Contents

- [Overview](#overview)
- [Tools Installed](#tools-installed)
- [Prerequisites](#prerequisites)
- [Step-by-Step Setup](#step-by-step-setup)
  - [Step 1 — Install Cursor IDE](#step-1--install-cursor-ide)
  - [Step 2 — Install the Claude Code Extension](#step-2--install-the-claude-code-extension)
  - [Step 3 — Install the Codex Extension](#step-3--install-the-codex-extension)
  - [Step 4 — Create a GitHub Repository](#step-4--create-a-github-repository)
  - [Step 5 — Open the Repository in Cursor](#step-5--open-the-repository-in-cursor)
  - [Step 6 — Create This README](#step-6--create-this-readme)
  - [Step 7 — Commit and Push to GitHub](#step-7--commit-and-push-to-github)
- [Issues Encountered & Solutions](#issues-encountered--solutions)
- [Final Result](#final-result)

---

## Overview

This repository documents the setup process for a modern AI-assisted development environment using:

- **Cursor** — an AI-first code editor built on top of VS Code
- **Claude Code** — Anthropic's AI coding extension that brings Claude directly into the editor
- **Codex** — OpenAI's code intelligence extension
- **GitHub** — version control and remote repository hosting

---

## Tools Installed

| Tool | Version / Source | Purpose |
|------|-----------------|---------|
| [Cursor IDE](https://cursor.com/) | Latest stable — cursor.com | AI-first code editor (VS Code fork) |
| [Claude Code Extension](https://marketplace.cursoride.com/) | Installed via Cursor Extensions | Anthropic's Claude AI assistant in the editor |
| [Codex Extension](https://marketplace.cursoride.com/) | Installed via Cursor Extensions | OpenAI Codex code intelligence |
| Git | v2.39.5 (Apple Git, pre-installed on macOS) | Version control |
| GitHub CLI (`gh`) | Pre-installed, authenticated | Create/manage GitHub repos from terminal |
| macOS | Darwin 24.6.0 | Operating system |

---

## Prerequisites

Before starting, make sure you have:

- A Mac running macOS (these steps are macOS-specific)
- A [GitHub account](https://github.com/) — free to create
- An [Anthropic account](https://console.anthropic.com/) — for Claude Code sign-in
- An [OpenAI account](https://platform.openai.com/) — for Codex sign-in
- Internet connection

---

## Step-by-Step Setup

### Step 1 — Install Cursor IDE

1. Go to [https://cursor.com/](https://cursor.com/)
2. Click **Download for Mac**
3. Open the downloaded `.dmg` file
4. Drag the **Cursor** app into your `/Applications` folder
5. Open Cursor from Applications (macOS may prompt you to confirm — click **Open**)
6. Complete the initial onboarding (choose a theme, import VS Code settings if desired)

> **What is Cursor?**
> Cursor is a fork of VS Code built with AI at its core. It supports all VS Code extensions, themes, and keybindings, but adds deep AI features like multi-file edits, codebase-aware chat, and inline AI completions powered by models like Claude and GPT-4.

---

### Step 2 — Install the Claude Code Extension

1. Open Cursor
2. Press **`Cmd+Shift+X`** to open the Extensions panel (or click the grid icon in the left sidebar)
3. In the search bar, type **`Claude Code`**
4. Find the extension published by **Anthropic** and click **Install**
5. Once installed, an Anthropic icon will appear in the left activity bar
6. Click it and follow the sign-in flow using your Anthropic account

> **What is Claude Code?**
> Claude Code is Anthropic's official extension that integrates Claude AI directly into your editor. It can answer questions about your codebase, write and edit code across multiple files, run terminal commands, and act as an autonomous coding agent. It uses context from your open files and project structure to give highly relevant responses.

> **Note:** If you don't see the extension immediately after searching, try switching the extension source from the Cursor marketplace to the **VS Code Marketplace** using the dropdown at the top of the Extensions panel.

---

### Step 3 — Install the Codex Extension

1. With the Extensions panel still open (`Cmd+Shift+X`), clear the search and type **`Codex`**
2. Find the Codex extension by **OpenAI** and click **Install**
3. After installation, you'll be prompted to sign in with your OpenAI account or enter an API key
4. Get your API key from [https://platform.openai.com/api-keys](https://platform.openai.com/api-keys)
5. Paste the key when prompted and confirm

> **What is Codex?**
> OpenAI Codex is a code-focused AI model trained on billions of lines of code. The Cursor extension uses it to provide intelligent code completions, docstring generation, and code explanation directly inside the editor.

---

### Step 4 — Create a GitHub Repository

**Option A — GitHub CLI (terminal):**

```bash
# Authenticate if not already logged in
gh auth login

# Create a new public repository
gh repo create cursor-setup-task --public --description "Cursor IDE + Claude Code + Codex setup documentation"

# Initialize local git repo and link it
mkdir cursor-setup-task
cd cursor-setup-task
git init
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/cursor-setup-task.git
```

**Option B — GitHub website:**

1. Go to [https://github.com/new](https://github.com/new)
2. Enter `cursor-setup-task` as the repository name
3. Set visibility to **Public**
4. Click **Create repository**
5. Follow the instructions shown to push an existing local repo

---

### Step 5 — Open the Repository in Cursor

**Option A — From terminal (requires Cursor CLI in PATH):**

```bash
cursor /path/to/cursor-setup-task
```

To install the `cursor` CLI command: open Cursor → `Cmd+Shift+P` → type **"Install 'cursor' command in PATH"** → press Enter.

**Option B — From within Cursor:**

1. Go to `File → Open Folder...`
2. Navigate to and select your `cursor-setup-task` folder
3. Click **Open**

---

### Step 6 — Create This README

Inside the open project in Cursor, create a new file called `README.md` and document your setup process. This file is that documentation.

You can create it from the terminal:

```bash
touch README.md
```

Or from within Cursor using `File → New File`.

---

### Step 7 — Commit and Push to GitHub

```bash
# Stage the README
git add README.md

# Commit with a descriptive message
git commit -m "Add setup documentation for Cursor IDE, Claude Code, and Codex"

# Push to GitHub
git push -u origin main
```

Verify it's live by visiting:
`https://github.com/YOUR_USERNAME/cursor-setup-task`

---

## Issues Encountered & Solutions

| # | Issue | Root Cause | Solution |
|---|-------|-----------|----------|
| 1 | `cursor` CLI command not in PATH | Cursor doesn't auto-install the CLI on first launch | Opened Cursor → `Cmd+Shift+P` → "Install 'cursor' command in PATH" |
| 2 | Claude Code extension not showing up in search | Cursor's own marketplace has a smaller index than VS Code's | Switched the extension source dropdown to **VS Code Marketplace**, then searched again |
| 3 | Claude Code sign-in screen not loading | Cursor was opened without a folder — some extensions require an active workspace | Opened a folder first (`File → Open Folder`), then the sign-in flow worked |
| 4 | Codex prompted for API key, not OAuth | Codex uses API key auth, not account login | Retrieved key from [platform.openai.com/api-keys](https://platform.openai.com/api-keys) and pasted it in |
| 5 | `git push` rejected on first push | Remote had no tracking branch set | Used `git push -u origin main` to set upstream and push simultaneously |

---

## Final Result

- **Cursor IDE** installed and running on macOS
- **Claude Code** extension active and signed in — accessible via the sidebar
- **Codex** extension active with API key configured
- **GitHub repository** live and public at:
  [https://github.com/ngtswaz/cursor-setup-task](https://github.com/ngtswaz/cursor-setup-task)
- This **README.md** committed and pushed as proof of completion

---

*Setup completed on macOS Darwin 24.6.0 — June 2026*
