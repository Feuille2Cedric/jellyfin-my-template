# Jellyfin CSS Tweaks

This repo contains a small set of Jellyfin UI tweaks layered on top of the Scyfin theme.
The goal is to keep the interface clean and focused while leaving the base Scyfin look intact.

## Features
- Import the Scyfin theme as a base.
- Hide the **Music** tile on Home and remove **Music** from the sidebar.
- Tighten spacing on the Home cards to avoid awkward gaps.
- Keep only playlists whose name contains `f2c__` (others are hidden).

## What This CSS Targets
- **Home page tiles**: removes the Music tile by targeting links that point to `/music`.
- **Sidebar**: hides the Music entry to keep navigation minimal.
- **Playlists page**: filters cards by checking playlist name attributes.

## Install
1. Open Jellyfin Dashboard.
2. Go to `General` > `Custom CSS`.
3. Paste the CSS from this repo and save.

## Customize
- Want a different tag than `f2c__`?
  - Replace every `f2c__` in the CSS with your own keyword.
- Want Music to stay visible?
  - Remove the Home + sidebar blocks and keep only the playlist filter.

## Notes
- Uses the `:has()` selector, so your Jellyfin client/browser must support it.
- The playlist filter relies on Jellyfin placing the name in `title` or `aria-label`.
  If a client does not expose those attributes, filtering will not work there.

## Troubleshooting
- If nothing shows on Playlists:
  - Your client likely doesn’t support `:has()`.
  - Try another client (desktop browser) or remove the filter block.
