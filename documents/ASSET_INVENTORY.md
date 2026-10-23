> Public showcase copy of game handover documentation. Game-source paths, JSON manifests, tests and build artifacts mentioned below refer to the separate private buyer package. They are not included in this public repository. Original report dates are retained.

# TRASH EMPIRE asset inventory

Version 1.0.0. The accompanying `ASSET_INVENTORY.json` lists every editable game asset: relative path, file type, byte size, SHA-256, origin and applicable notice. Rebuild with `python tools/build_asset_inventory.py`.

**373 assets; 17,332,393 bytes.** Godot `.import` metadata is excluded from the asset count but included in the source manifest. Runtime drawing code, scene files, localization and all other source files are covered by `SOURCE_MANIFEST.json`.

| Type | Files |
|---|---:|
| fnt | 1 |
| json | 2 |
| mid | 3 |
| ogg | 3 |
| png | 11 |
| svg | 320 |
| ttf | 1 |
| wav | 32 |

## Provenance and limits

Artwork is editable SVG or project-generated raster material created with Codex assistance. Nunito has OFL terms; Yard Symbols is original CC0 artwork. Audio includes 27 credited CC0 effects, three Codex-assisted original music performances rendered with GeneralUser GS instruments, and five original procedurally synthesized mentor clips. Each recording retains author, source and checksums in `assets/audio/catalog.json`.

Original-material transfer terms belong in the seller/buyer agreement. Third-party assets remain under their original terms. AI assistance is disclosed; this inventory does not certify exclusivity, trademark clearance or copyright eligibility. GeneralUser GS historical sample-origin limitations are retained in its license. See `THIRD_PARTY_LICENSES.md` and `KNOWN_ISSUES.md` before agreeing commercial rights.

Optional source caches, the SoundFont bank, FluidSynth, FFmpeg, the engine binary, SDK/JDK, signing keys and editor caches are not supplied. Existing finished assets are included and export without those optional generators.
