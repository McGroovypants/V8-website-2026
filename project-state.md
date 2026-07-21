# Vision8 editor project state

## Version

v1.0, baseline recorded 21 July 2026.

## Purpose

Turn the Vision8 website editor into a reliable content editor that follows the live preview and preserves the approved site design.

## Source of truth

- Repository: `McGroovypants/Vision8Website`
- Current baseline commit: `6255e37`
- Main files: `index.html`, `editor/index.html`
- Baseline source copies and checksums: `backups/v1.0-baseline/`

## Confirmed requirements

1. Remove the four-card statistics section: 25+, 500+, 9 and 100%.
2. Repair the logo workflow. It must be a real image field with paste-URL and upload options.
3. The editing panel must follow the preview screen while scrolling, and preview-to-editor selection must work too.
4. Make existing content editable without allowing arbitrary layout changes: text, images, videos, URLs, button labels, modal content, contact details, navigation, footer and site settings.
5. Add an explicit top-video sizing control. Full-screen must be one option, not a fixed decision.
6. Work in small stages. Each stage needs a focused test, a version increment, a source snapshot, state update and a Git commit.
7. Use Git commits as the durable handover, so the work remains available in VS Code and does not rely on chat memory.

## Known defects and risks

- The current logo is an anchor treated as text, not an image. A pasted URL is therefore rendered as text, producing the blank logo area.
- Image upload does not reliably persist its new asset URL into the generated site markup.
- The editor currently contains a publishing credential. It must be removed from browser code and rotated before production use.

## Delivery stages

### v1.1, content hygiene

Remove statistic cards; repair logo image URL and upload; remove the browser-held publishing credential; test preview and saved output.

### v1.2, linked editing

Add bidirectional preview and editor focus behaviour. Selecting an editable preview item opens and scrolls its matching control; focusing a control reveals the matching preview item.

### v1.3, hero controls

Add top-video sizing presets and a custom height option, with desktop and mobile previews. Keep full-screen as an available preset.

### v1.4, comprehensive content fields

Expose remaining existing text, images, videos, links, buttons, modal material, navigation, contact and footer fields.

### v1.5, content structure

Add controlled hide/show, reorder and add/delete functions for repeatable content groups.

## Change controls

- Do not make unrequested design changes.
- Keep layout choices constrained to approved controls, not free-form styling.
- Read the target file before every edit.
- Review the diff after every stage. Do not include unrelated changes.
