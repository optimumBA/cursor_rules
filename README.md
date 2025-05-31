# Optimum Cursor rules

Cursor rules suitable for development using Elixir and Phoenix.

## 🚨 CRITICAL: Fix Cursor .mdc Editor Bug First

**Before using these rules**, you must fix a critical bug in Cursor's .mdc file handling:

Cursor's custom .mdc editor is severely buggy and causes multiple issues:

- **Cursor jumps to description field during editing**
- **Auto-save disrupts workflow and causes focus issues**
- **Agent thinks it's editing files but changes don't persist to filesystem**
- **Files may appear empty when they contain content**

### Fix Required

Add this to your Cursor settings to disable the custom .mdc editor:

```json
"workbench.editorAssociations": {
  "*.mdc": "default"
}
```

**How to apply**:

1. Open Cursor Settings (Cmd/Ctrl + ,)
2. Search for "editorAssociations"
3. Add the mapping above
4. Restart Cursor if needed

This treats .mdc files as regular markdown, eliminating all editing bugs.

## Setup

Add the repo as a git submodule to your Phoenix app.

```bash
git submodule add https://github.com/optimumBA/cursor_rules .cursor/rules
```

Rules should automatically be applied by Cursor.  
They can live side-by-side with your existing rules.

## Updating

To update the Cursor rules to the latest version:

```bash
git submodule foreach git checkout main && git pull
```

This ensures you get the latest improvements and bug fixes to the rules.
