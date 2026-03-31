# amp-doc

Create and edit native Google Docs in Amplitude's workspace using Google Apps Script. All documents use Poppins font throughout with consistent heading hierarchy and Amplitude Blue accents.

## What it does

- Creates new Google Docs or edits existing ones (by URL)
- Full typography system: title, H1–H3, body, captions — all Poppins
- Supports bullet lists, numbered lists, tables, horizontal rules, and images
- Writing-quality-first approach: clear, direct prose with no filler

## Requirements

- Claude Desktop with Cowork mode
- Claude in Chrome extension (connected and active)
- Google account with Docs access

## First-run setup

Handled automatically on first use. The skill creates a "Doc Builder" Apps Script project and walks you through Google's OAuth authorization. No manual configuration needed.

## How it works

1. You describe the document you want (or provide a URL to edit)
2. The skill drafts the content, then generates Apps Script code (`buildDoc()`)
3. Injects the full file (helpers + buildDoc) into the Apps Script editor via Chrome's Monaco editor (3-phase keyboard trigger approach)
4. Saves and runs the script
5. Navigates to the doc to verify formatting

## Installing

See the [repo README](../../README.md) for packaging and installation instructions.

## Version

Current: **0.3.0**
