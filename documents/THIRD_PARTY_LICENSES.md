> Public showcase copy of game handover documentation. Game-source paths, JSON manifests, tests and build artifacts mentioned below refer to the separate private buyer package. They are not included in this public repository. Original report dates are retained.

# TRASH EMPIRE licensing and provenance

This document covers version 1.0.0. Full notices are retained in `licenses/` and accessible in the game's Settings. Read `THIRD_PARTY_NOTICES.md` for component details and links. The per-file `ASSET_INVENTORY.json` and audio catalog identify individual asset origins and hashes.

| Material | License or rights basis | Included evidence |
|---|---|---|
| Godot 4.5.1 runtime and dependencies | MIT and engine dependency licenses | `licenses/GODOT-LICENSE.txt`, `licenses/GODOT-THIRD-PARTY.txt` |
| Nunito | SIL Open Font License 1.1 | `licenses/NUNITO-OFL.txt` |
| Yard Symbols bitmap font | Original project geometry, CC0 1.0 | `licenses/YARD-SYMBOLS.txt` |
| 27 field/UI/vehicle/machine effects | Third-party CC0 1.0 recordings | `licenses/AUDIO-CREDITS.txt`, `licenses/audio/`, `assets/audio/catalog.json` |
| Three music tracks, score and MIDI | Original project score made with Codex assistance; sampled instruments subject to GeneralUser GS license | `assets/audio/music/score.json`, MIDI files, `licenses/GENERALUSER-LICENSE.txt` |
| Five mentor effects | Original procedural nonverbal synthesis, made with Codex assistance | `tools/build_yard_polish.py`, preserved hashes in audio catalog |
| Project GDScript, SVG, authored data/dialogue | Project material made with Codex assistance; transfer governed by the seller/buyer agreement | Editable sources and `LICENSE.txt` |

There are no neural audio-generator outputs in the current audio catalog. Music was rendered from explicitly written note data using sampled instruments. The mentor effects are procedural synthesis, not recorded speech or a cloned human voice. The commercial package does not describe these assets as entirely human-created or as exclusive third-party-free material.

GeneralUser GS permits commercial recordings, but its retained license describes uncertainty about the historical origin of some instrument samples. The buyer must assess that limitation before accepting rights or publishing. Replace the affected music with independently cleared performances if the buyer requires stronger provenance. No exclusive ownership of the instrument samples is transferred.

Development dependencies (Godot editor/templates, Python packages, FFmpeg, FluidSynth, instrument bank, JDK and Android SDK) are installed separately and excluded from this archive. If the buyer redistributes those tools, their own notices and redistribution requirements apply. Existing assets can be exported without rebuilding the optional generators.

The sale agreement must define the original-material license, source-code transfer, permitted reuse, exclusivity if any, support and warranty terms. This inventory is an evidence record, not a legal opinion or a guarantee of copyright/trademark clearance.
