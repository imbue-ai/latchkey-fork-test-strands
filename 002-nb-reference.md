# NB - Reference - Common Commands

Tags: #cheatsheet #nb #commands #reference

## Purpose

Quick reference for the most useful `nb` commands, extracted from project documentation.

---

## Quick Reference

```bash
nb list -sr | head -n 20
```
List notes sorted by recency with titles.

```bash
nb show 12 --print --no-color
```
View note by ID.

```bash
nb search '#keyword' | head
```
Search notes by tag.

```bash
nb sync --all
```
Manually sync with remote.


Adding/editing notes: (always use --overwrite and heredocs!)

```bash
# Write content to temp file
cat << 'EOF' > /tmp/note-content.md
# Title

Tags: #tag1 #tag2

Content here...
EOF

# Load into nb edit
nb edit <id> --content "$(cat /tmp/note-content.md)" --overwrite

# Clean up
rm /tmp/note-content.md
```

## Essential tips

1. **Always search first**: Before creating docs, run `nb search '#keyword' | head` to check for existing coverage.

2. **Use `-sr` for listing**: `nb list -sr` shows titles sorted by recency, much more useful than plain `nb list`.

3. **Always use `--overwrite`**: When using `nb edit --content`, omitting `--overwrite` appends content and creates duplicates.

4. **Include nb numbers in links**: When referencing notes, use format `[[Title]] (nb N)` for easy navigation.

---
Created-by: initial template
