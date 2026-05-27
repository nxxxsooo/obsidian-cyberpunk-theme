# obsidian-cyberpunk-theme

## Overview
Cyberpunk neon theme for Obsidian. Ported from channingwalton's Typora Cyberpunk theme with intense neon glow, grid backgrounds, glitch effects.

## Architecture
Single-file theme: `theme.css` + `manifest.json`. No build step.

## Key Files
- `theme.css` — All styles (CSS variables + rules)
- `manifest.json` — Theme metadata and version

## Patterns & Conventions
- CSS variables declared in `.theme-dark {}` block (lines 16-254)
- Style rules organized by section with `═══` comment headers
- Colors: cyan (#00f5ff), pink (#ff006e), purple (#b300ff), green (#39ff14), yellow (#ffed00)
- Font: Rajdhani (Google Fonts import) + PingFang SC fallback

## Deployment
- **Source**: `GitHub/obsidian-cyberpunk-theme/theme.css`
- **Production**: `Vault/.obsidian/themes/Cyberpunk/theme.css`
- Obsidian reads from Vault, NOT GitHub. Edit Vault copy for testing, sync to GitHub for release.
- The Vault copy has additional tweaks (wider line-width, spacing, blockquote decorations)

## Resolved Issues
- **v1.1.0**: Sidebar collapse/expand cumulative indentation shift. Root cause: `transition: all` on nav items caused Obsidian JS to read mid-animation `padding-inline-start` values and accumulate them. Fix: explicit transition properties only.
- **v1.1.0**: Active nav item `border-left: 3px` caused layout shift. Fix: `box-shadow: inset 3px 0 0`.
