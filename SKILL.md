---
name: repair-ui-copy
description: Use when a Vue or dashboard UI shows garbled copy, literal question-mark placeholders, broken toast text, encoding damage after shell edits, or long labels that overflow cards, dialogs, or badges.
---

# Repair UI Copy

## Overview
Treat broken UI copy as a real defect, not as cosmetic noise. Fix the source strings, keep files in valid UTF-8, and harden text containers so long content does not blow up the layout.

## Quick Reference
- Search for literal question-mark placeholder strings first.
- Replace corrupted text at the source instead of masking it in CSS.
- Keep toast copy short and explicit.
- Add `break-words`, `break-all`, or `line-clamp-*` where labels can grow.
- Re-run a content check so no broken placeholders remain.

## Workflow
1. Scan the affected files for placeholder garbage, mojibake, and visibly corrupted strings.
2. Replace the source copy with explicit UTF-8 text.
3. Review recent shell-write steps if corruption appeared after scripting.
4. Add text overflow guards on cards, dialogs, and metadata rows.
5. Validate that the UI no longer contains placeholder garbage.

## Common Mistakes
- Fixing the rendered HTML while leaving corrupted source strings behind.
- Using shell quoting that rewrites non-ASCII copy incorrectly.
- Letting long project names or role labels overflow fixed-width cards.
- Writing verbose toast messages when the user wanted a short confirmation.

## Example
Use when the user says: "Fix these question marks", "the toast text is broken", or "long labels overflow the card".
