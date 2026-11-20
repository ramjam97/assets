# Assets

A centralized assets server for my projects. This repository hosts shared images — company/organization logos and project screenshots — so every project can reference the same files through stable, public URLs instead of duplicating them.

## Why

- **Single source of truth** — update an asset once and every project sees the change.
- **No bundling needed** — assets are served directly from GitHub, keeping project repositories lightweight.
- **Public and hotlinkable** — files are available over HTTPS via `raw.githubusercontent.com`.

## Structure

```text
assets/
├── logo/       # Company and organization logos
│   └── url-path.txt
└── projects/   # Screenshots and preview images of projects
    └── url-path.txt
```

Each directory contains a `url-path.txt` with its base URL and a usage example.

## Usage

Reference an asset directly with its raw GitHub URL. The general pattern is:

```text
https://raw.githubusercontent.com/ramjam97/assets/refs/heads/master/<directory>/<filename>
```

### Base URLs

| Directory | Base URL |
| --- | --- |
| `logo/` | `https://raw.githubusercontent.com/ramjam97/assets/refs/heads/master/logo/` |
| `projects/` | `https://raw.githubusercontent.com/ramjam97/assets/refs/heads/master/projects/` |

### Examples

```html
<!-- Company logo -->
<img src="https://raw.githubusercontent.com/ramjam97/assets/refs/heads/master/logo/EPCPS.jpg" alt="EPCPS logo">

<!-- Project screenshot -->
<img src="https://raw.githubusercontent.com/ramjam97/assets/refs/heads/master/projects/wisa-gba.png" alt="WiSA GBA screenshot">
```

```css
.hero {
  background-image: url("https://raw.githubusercontent.com/ramjam97/assets/refs/heads/master/projects/tempest.png");
}
```

## Adding assets

1. Place the file in the appropriate directory (`logo/` or `projects/`).
2. Keep filenames short, lowercase, and hyphenated (for example, `qr-code-generator-website.png`).
3. Commit and push to `master`.
4. Reference the file using the base URL for its directory.

> Note: `master` is used in the URLs, so always push changes to that branch for them to be available.
