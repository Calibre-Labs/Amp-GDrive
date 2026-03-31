# Amp-GDrive

Cowork plugins for creating native Google Docs and Slides in Amplitude's workspace using Google Apps Script.

## Plugins

| Plugin | Description |
|--------|-------------|
| `amp-doc` | Create and edit Google Docs in Amplitude's workspace with Poppins typography |
| `amp-slide` | Create Google Slides in Amplitude's brand style |

Both plugins use Claude in Chrome to inject and run Apps Script — no manual coding required.

## Quick setup with Claude CoWork (recommended)

If you use Claude CoWork, you don't need to package or install anything manually — Claude handles the full setup.

1. **Clone this repo** and open a CoWork session
2. **Mount the cloned folder** in CoWork (drag it in or use the folder picker)
3. **Ask Claude to set up the plugin you want**, e.g.:
   > "Set up the amp-slide plugin from this repo"

   Claude will:
   - Package the plugin into a `.plugin` file
   - Install it into your CoWork session
   - Open `script.google.com` in Chrome and create the Apps Script project
   - Run a test function to trigger Google's OAuth dialog
   - Walk you through approving permissions

4. Once OAuth is approved, **ask Claude to create a test doc or slide** to confirm everything works:
   > "Create a test slide with a title and one bullet point"

That's it — the plugin is ready to use for future requests.

> **Note:** Make sure your Amplitude Google account is active in Chrome before step 3. Claude will check and prompt you to switch if needed.

---

## Manual install (without CoWork)

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
