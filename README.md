# Cursor Configuration Stow

A simple shell script to manage Cursor editor configuration files using symlinks.

## What it does

This script creates symbolic links from your Cursor configuration files to a centralized location, making it easy to version control and sync your Cursor settings across machines.

## Files managed

- `keybindings.json` - Custom keyboard shortcuts
- `settings.json` - Editor preferences and settings

## Usage

```bash
./stow
```

## How it works

1. **Backup**: Creates backups of existing configuration files in `~/Library/Application Support/Cursor/User/bk/`
2. **Symlink**: Creates symbolic links from the current directory's config files to Cursor's config directory

## Requirements

- macOS (uses `~/Library/Application Support/Cursor/User/` path)
- Cursor editor installed

## Configuration

Edit the `FILES` array in the script to add/remove files you want to manage:

```bash
FILES=("keybindings.json" "settings.json" "extensions.json")
```

## Restore from backup

If you need to restore from a backup, copy the file from the backup directory:

```bash
cp ~/Library/Application\ Support/Cursor/User/bk/settings.json ~/Library/Application\ Support/Cursor/User/settings.json
```
