# Prosper Calendar branding

This repository is a fork of [keeper.sh](https://github.com/ridafkih/keeper.sh) by Rida F'kih,
licensed under AGPL-3.0 (see `LICENSE` and `NOTICE`, both unchanged). The modified source is
published here as the license requires. Branding changes are kept small so upstream merges stay easy.

## Changed files (all under `applications/web/`)
| File | Change |
|---|---|
| `src/lib/seo.ts` | `SITE_NAME` / `SITE_ALTERNATE_NAME` → "Prosper Calendar" |
| `src/routes/__root.tsx` | `<title>` → "Prosper Calendar" |
| `src/routes/(auth)/login.tsx`, `register.tsx` | Subtitle copy |
| `src/assets/keeper.svg` | Replaced with the Prosper Manufacturing globe mark (`currentColor`) |
| `public/keeper.svg`, `public/keeper-dark.svg` | Favicon: navy / white Prosper mark |
| `public/*.png`, `public/favicon.ico` | Prosper app icons (from prosper-customer-portal) |
| `public/site.webmanifest` | Name and navy/white colors |
| `src/index.css` | One appended `:root` block: navy `#0B1F3A` text, white background, royal `#1E5BFF` focus ring |

Plus `.github/workflows/prosper-images.yml` (GHCR build) and this file.

## Merging upstream
`git fetch upstream && git merge upstream/main`, then fix any conflicts in the files above (keep ours).
File names were kept the same (e.g. `keeper.svg`) so imports never change.

## Command-center theme (v2.28.8-prosper.2)
Matches portal.prosper-mfg.tech (prosper-customer-portal):
- Font: Blinker 400/600/700 (`public/assets/fonts/Blinker-*.woff2`, self-hosted), used for sans and the serif heading slot; tabular numerals.
- Colors: canvas `#F4F2EE` page bg, white cards, navy `#0B1F3A` text/primary buttons, muted `#4B5563`, hairlines `#E4E2DD`, royal `#1E5BFF` focus ring, danger `#DC2626`, warning `#D97706`.
- `__root.tsx` preloads Blinker instead of Lora. Keeper is light-only upstream, so only the portal's light tokens apply.
