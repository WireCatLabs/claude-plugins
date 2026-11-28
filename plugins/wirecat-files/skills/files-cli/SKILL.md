---
name: files-cli
description: >-
  Search the owner's notes folders, Obsidian vaults and imported PDF and Word files through files, and add a folder or a file to the local store. Use when asked to find something in the owner's notes or documents on this computer.
metadata:
  openclaw:
    requires:
      bins: [files]
    install:
      - kind: node
        package: "@wirecat/files-cli"
        bins: [files]
---

# files: the owner's notes and documents on this computer

files reads the folders and files the owner chose into the local WireCat store. It never changes them.

- `files search notes '<a few key words>' --limit 10 --compact` searches the imported notes and documents.
- `files folders list` shows the folders it reads. `files folders add <path>` and `files sync` bring a new folder in.
  Ask the owner before adding a folder.
- `files sources add` keeps pasted text, a file or a public page. `files import` reads a PDF, Word file or transcript.
- Across messages, mail and notes together, use `wcat search all`.
- `files commands` lists every command, `files doctor --json` checks the setup.
