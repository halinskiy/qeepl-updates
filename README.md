# Qeepl

A zoomable macOS canvas for terminals, VS Code, browsers and notes, with remote
terminals from another Mac and CLI/MCP control for agents working in the background.

## Download

- [Latest release](https://github.com/halinskiy/qeepl-updates/releases/latest)
- Current release: [0.4.47 · build 101](https://github.com/halinskiy/qeepl-updates/releases/tag/v0.4.47)
- [Download Qeepl 0.4.47 DMG](https://github.com/halinskiy/qeepl-updates/releases/download/v0.4.47/Qeepl-0.4.47.dmg)
- [Download Qeepl 0.4.47 ZIP](https://github.com/halinskiy/qeepl-updates/releases/download/v0.4.47/Qeepl-0.4.47.zip)

Open the DMG and drag Qeepl to Applications. The app and DMG are signed with
Developer ID and notarized by Apple.

Installed copies download updates through Sparkle and show **Restart to Update**.
An unattended Mac can install once its terminals are idle. The **Check for Updates…**
menu command requests installation when the update is ready.

## In 0.4.47

- **Find windows:** Cmd+F searches titles, including locked and remote windows. The
  camera moves to each result and highlights the matching title text in yellow.
  Enter / Shift+Enter moves between results; Escape closes search.
- **Locked window opacity:** View → Locked Window Opacity adjusts visibility from
  5% to 100%. The setting persists, and locked windows still let clicks pass through.
- **Minimap status:** working terminals and terminals waiting for a reply are blue;
  finished terminals are muted red; locked windows keep fine diagonal hatching.
- **Remote file drop:** drag regular files onto a remote terminal. Qeepl copies them
  to the host Mac, verifies their size and SHA-256, and pastes quoted paths into that
  terminal without pressing Enter or replacing the clipboard.
- **Codex restore:** explicit conversation IDs survive npm launcher wrappers.
  Verified window-to-conversation bindings are stored separately from profiles;
  restoration no longer guesses a conversation from transcript modification times.
  The same checks apply when unlocking a frozen terminal.

Remote file drop requires **0.4.47 or later on both Macs**. Folders and symbolic links
are not supported; a folder can be sent as an archive. Limits are 64 files, 1 GiB per
file and 2 GiB per drop. A successful transfer means paths were delivered to the
terminal, not that the program inside has processed the files.

For an old Codex window with only an unresolved `--last`, Qeepl restores the saved
screen and a shell instead of choosing a conversation. Switching conversations with
`/resume` inside a running Codex process is not yet reliably detected.

## Quick controls

- Cmd+N / Cmd+T: new terminal; Cmd+B: browser; File → Open VS Code…: editor.
- Two-finger scroll: move the canvas. Option+scroll: scroll the window under the pointer.
- Cmd+F: find a Qeepl window, including when VS Code has focus. Editor text search remains
  available through its Edit → Find menu or command palette.
- Hold Cmd+Q for two seconds to quit; a white line at the bottom shows progress.

## Update feed

[Sparkle appcast](https://halinskiy.github.io/qeepl-updates/appcast.xml)

This repository hosts the signed release artifacts and update feed on `gh-pages`.
