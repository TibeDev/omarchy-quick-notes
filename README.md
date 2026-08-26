# Quick Notes

Quick notes for the Omarchy bar. A sticky-note icon lives in your bar; click
it to open a popup where you can create, edit, and delete short notes.

## Install

```sh
omarchy plugin add https://github.com/tibevdb/quick-notes.git --enable
```

## Usage

- Click the  icon in the bar to open the notes panel.
- Click **+** to create a new note.
- Click a note in the list to open it for editing. Title and body save
  automatically as you type (or press **Ctrl+S** for an explicit save).
- Click the trash icon (on a row, or **Delete** in the editor) to delete a
  note, then confirm.

### Keyboard

The whole panel is navigable with arrows - no mouse required:

- Arrow keys / `hjkl` move the keyboard cursor around: through the note
  list and the **+** button in the list view, and through
  Back / Title / Body / Delete in the editor.
- **Enter** / **Space** activates whatever the cursor is on - opens a note,
  creates one, enters a text field to type, or triggers Delete/Back.
- In the list: `n` creates a new note, `x` deletes the selected one.
- **Escape**: while typing in a field, the first press leaves typing mode
  and returns to browsing the editor's controls; press it again to go back
  to the list; once more to close the panel.
- **Ctrl+N** starts a new note from anywhere in the panel. While a note is
  open for editing, **Ctrl+S** saves immediately and **Ctrl+Backspace**
  deletes the note - both work no matter where the focus is.

### Storage

Notes are stored as plain JSON at
`~/.local/state/omarchy/plugins/quick-notes/notes.json`.
Storage is bounded to keep the shell process healthy even if that file is
hand-edited or replaced: up to 500 notes, 200 characters per title, 20,000
characters per body, and a 12 MiB total file size. The file's size is
checked on disk (via `stat`, without reading its content) before it is ever
loaded; an oversized file is rejected rather than read into memory.

## Remove

```sh
omarchy plugin remove quick-notes
```

## Disclaimer

This plugin was vibe coded with [Claude Code](https://claude.com/claude-code).
