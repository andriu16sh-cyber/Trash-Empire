# Public showcase scope

Prepared 23 October 2026. This package replaces the earlier, broader public
website package with a media-and-documentation-only GitHub showcase.

Included:
- An English README with website and SideProjectors links.
- Eight flattened screenshots or promotional images and one gameplay video.
- Four public game reports, with their original test dates and coverage limits.
- Publication instructions, existing-rights notice and video audio notices.
- Verification results and a SHA-256 manifest.

Excluded:
- Standalone textures, sprites, SVGs, models and other editable game artwork.
- Individual sound files, font binaries, game data, translations and generators.
- Game source, scenes, the Godot project and Android APK/AAB builds.
- Website source and its individual illustrations.
- The private buyer archive, signing keys, credentials and local configuration.
- Git history, development tools, caches, personal saves and private contact data.

The PNGs are complete game captures and a presentation cover, not extracted
texture assets. Any public image or video can still be downloaded and copied.

The .gitignore uses an explicit allowlist of these files. A future public file
must be intentionally added to that list before normal Git staging includes it.
PUBLIC_MANIFEST.json lists the exact files and hashes, excluding itself.

This package changes only the GitHub materials. The separately published
presentation website is not changed by assembling this archive.
