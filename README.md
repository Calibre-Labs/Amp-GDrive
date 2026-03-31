# Amp-GDrive

Cowork plugins for creating native Google Docs and Slides in Amplitude's workspace using Google Apps Script.

## Plugins

| Plugin | Description |
|--------|-------------|
| `amp-doc` | Create and edit Google Docs in Amplitude's workspace with Poppins typography |
| `amp-slide` | Create Google Slides in Amplitude's brand style |

Both plugins use Claude in Chrome to inject and run Apps Script — no manual coding required.

## Installing

### Prerequisites

- Claude Desktop with Cowork mode enabled
- Claude in Chrome extension installed and connected
- A Google account with access to Amplitude's Google Workspace

### Steps

1. **Clone the repo**
   ```bash
   git clone https://github.com/Calibre-Labs/Amp-GDrive.git
   ```

2. **Package the plugin**

   `cd` into the plugin folder and zip it:
   ```bash
   # amp-doc
   cd Amp-GDrive/amp-doc
   zip -r ~/Desktop/amp-doc.plugin .claude-plugin skills -x "*.DS_Store"

   # amp-slide
   cd Amp-GDrive/amp-slide
   zip -r ~/Desktop/amp-slide.plugin .claude-plugin skills -x "*.DS_Store"
   ```

3. **Install in Cowork**

   Open Claude Desktop, go to Cowork mode, and drag the `.plugin` file into the session. The skill will appear in your available skills list.

4. **First-run setup**

   The first time you use either skill, it will:
   - Navigate to `script.google.com` via Chrome (ensure your Amplitude Google account is active)
   - Create a new Apps Script project ("Amp Doc Builder" or "Amp Slide Builder")
   - Walk you through granting Google OAuth permissions

   After this one-time setup, subsequent docs and slides are created automatically.

## Updating

When skills are updated:
```bash
git pull
cd amp-<doc|slide>
zip -r ~/Desktop/amp-<doc|slide>.plugin .claude-plugin skills -x "*.DS_Store"
```
Reinstall the `.plugin` file in Cowork to pick up the changes.

## Google Account Note

All Apps Script projects must run under your **Amplitude Google account**. Before first run, confirm the correct account is active in Chrome by checking `https://script.google.com` — the account shown in the top-right should be your `@amplitude.com` account. Use the `/u/N/` URL index to switch if needed.
