# amp-slide

Create native Google Slides in Amplitude's brand style using Google Apps Script. Generates `buildSlide()` functions, injects them into an Apps Script project via Chrome, and runs them to produce slides directly in Google Slides.

## What it does

- Builds individual slides or full decks in Amplitude's brand (Poppins font, Amplitude Blue `#1E61F0`, standard palette)
- 8 slide types: title, content + bullets, multi-column cards, stat callouts, section dividers, two-column text, quotes, image + text
- Title slides support decorative elements (constellation networks, "Made by Claude" badges) built from native Slides shapes
- In-place editing: modify existing slides without changing deck order

## Requirements

- Claude Desktop with Cowork mode
- Claude in Chrome extension (connected and active)
- Google account with Slides access

## First-run setup

Handled automatically on first use. The skill creates a "Slide Builder" Apps Script project and walks you through Google's OAuth authorization. No manual configuration needed.

## How it works

1. You describe the slide you want
2. The skill generates Apps Script code (`buildSlide()`)
3. Injects the code into the Apps Script editor via Chrome's Monaco editor (3-phase keyboard trigger approach)
4. Saves and runs the script
5. Takes a screenshot to verify the result

## Installing

See the [repo README](../../README.md) for packaging and installation instructions.

## Version

Current: **0.3.0**
