# Cursor IDE Setup — Tool Installation Log

## Tools Installed

| Tool | Version / Notes |
|------|-----------------|
| [Cursor IDE](https://cursor.com/) | Downloaded from cursor.com, macOS dmg installer |
| Claude Code (Cursor Extension) | Installed via Cursor Extensions panel — search "Claude Code", sign in with Anthropic account |
| Codex (Cursor Extension) | Installed via Cursor Extensions panel — search "Codex", sign in with OpenAI account |
| Git | v2.39.5 (pre-installed via Apple Git) |
| GitHub CLI (`gh`) | Pre-installed, authenticated via keyring |

---

## Steps Completed

1. **Downloaded and installed Cursor IDE** from [cursor.com](https://cursor.com/)
   - Opened the downloaded `.dmg`, dragged Cursor to `/Applications`
   - Launched Cursor and completed initial setup

2. **Installed Claude Code extension**
   - In Cursor: `Cmd+Shift+X` → searched "Claude Code" → clicked Install
   - Signed in with Anthropic account credentials

3. **Installed Codex extension**
   - In Cursor: `Cmd+Shift+X` → searched "Codex" → clicked Install
   - Signed in with OpenAI account credentials

4. **Created this public GitHub repository**
   - Created via GitHub CLI: `gh repo create cursor-setup-task --public`
   - Initialized with `git init` locally, set remote, pushed initial commit

5. **Opened the repository in Cursor**
   - Used `cursor /path/to/cursor-setup-task` from terminal (or File → Open Folder)

6. **Created this README.md** documenting the setup process

7. **Committed and pushed to GitHub**
   ```bash
   git add README.md
   git commit -m "Add setup documentation"
   git push -u origin main
   ```

---

## Issues Encountered & Solutions

| Issue | Solution |
|-------|----------|
| `cursor` CLI command not found after install | Opened Cursor, ran `Cmd+Shift+P` → "Install 'cursor' command in PATH" — resolved |
| Claude Code extension requires sign-in after install | Clicked the Anthropic icon in the Cursor sidebar → followed OAuth flow |
| Codex extension prompted for API key | Entered OpenAI API key from [platform.openai.com/api-keys](https://platform.openai.com/api-keys) |

---

## Repository

This repo was created as part of a tools setup exercise to document the installation of Cursor IDE and its AI coding extensions.
