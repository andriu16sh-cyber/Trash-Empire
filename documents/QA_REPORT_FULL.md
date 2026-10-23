> Public showcase copy of game handover documentation. Game-source paths, JSON manifests, tests and build artifacts mentioned below refer to the separate private buyer package. They are not included in this public repository. Original report dates are retained.

# TRASH EMPIRE full-project QA report

Version **1.0.0**, Android versionCode **32**. Recorded **2026-10-22T15:34:08.172948+00:00**. Godot **4.5.1 stable**, GDScript, Compatibility renderer, Windows native and headless execution.

**Local regression and build verification passed. Publisher-specific release gates remain open.** This report covers the full game source, not a restricted demo. It does not certify Google Play acceptance, exhaustive absence of defects or independent Android/BlueStacks runtime validation. The seller/user reports normal Android operation; device, OS and tested build checksum were not supplied, so this report does not assign that observation to the newly built APK.

## Product and preparation

The project includes three yards, recycling and finished-goods production, conveyors, changing demand, staff training and recovery, fleet routes, standing contracts, city restoration, bulky finds, a repair workshop and a shop with visiting customers. All 11 translations are retained. A fresh install starts in English; an existing explicit language choice persists.

Source comments, service metadata, buyer guides and reports are in English. Localized text lives under `i18n/`: canonical `.po` catalogs, language names, policy text, editorial source tables, authored dialogue sources and exact localized QA examples. Nine migrated Python modules were checked against their original syntax trees after reinserting extracted strings; values and types were preserved. Godot verifies that the legacy desktop save directory still resolves to the original location.

Preparation removed nine obsolete demo scripts, two associated scenes, three obsolete tests, eleven confirmed-unused methods, six unused Python imports and the obsolete garden-patch asset. Runtime resources with constructed paths, generator inputs and imports with intentional generation side effects were retained. Historical captures, stale builds, SDKs, credentials, caches and signing keys are excluded from the buyer archive.

## Verification results

| Check | Observed result |
|---|---|
| Full worktree regression | 77 groups / **19,885 checks**, zero failures; two completed model campaigns |
| Clean curated-source regression | 77 groups / 19,885 checks / 2 completed model campaigns |
| All shipped GDScript compilation | 307 scripts; no compilation failures |
| Runtime dependency graph | 157 of 157 runtime scripts reachable from the main scene |
| Python source parsing / formatting | 83 Python files; pinned Black / gdtoolkit formatting check passed |
| PowerShell / JSON / SVG | PowerShell syntax checked; source JSON parses; 320 SVG files parse |
| Native production/shop UI | 535 checks; 2442 text fields; no reported fit findings |
| Native language selection | 270 checks; 1276 text fields; 11 languages at four viewport sizes |
| Native legal pages and Back | 213 checks; 11 languages at three viewport sizes |
| Audio verification | 30 credited effects/music files: exact hashes, levels and loop seams; five mentor files unchanged; native mix checked |
| Language placement audit | No Cyrillic service prose outside `i18n/` in packaged text files |
| Editable game assets | 373 entries in per-file asset inventory; sizes, hashes and provenance recorded |
| APK | Release-mode evaluation certificate verified; separate package; API 24-36; four ABIs; no permissions; 16 KB alignment checked |
| AAB | Unsigned release build passes official bundletool validation, ABI/ELF/manifest checks and exact data/locale/license comparison |

Native repeats exercise parts of the regression and must not be added to the full regression count as independent coverage. Automated UI fit applies to the tested screens and sizes, not every possible device or every future text edit.

## Coverage and reproduction

Run `tests/run_tests.ps1 -GodotPath <Godot-console.exe> -KeepGoing` from the project. Tests use isolated save names. Read `README.md` for dependencies. `source_compile_test.gd` compiles every GDScript in `scripts`, `tests` and `tools`. The native UI tests run without `--headless`; `production_shop_profile.gd` runs separately with a 60 FPS cap and without `--fixed-fps` or concurrent builds/regressions.

Coverage includes save migration and damaged/missing-primary backup recovery; worker reservations, remote claims and 30-minute recovery scenarios; tutorial close/escape, repeated lessons, interaction targets, production input/output, automation, deliveries, trolley parking and cargo; layout and compound collisions; city restoration, restoration jobs and shop customers; touch scrolling, action buttons, long text, localization keys/plurals/glyphs and selected UI bounds; privacy/license navigation and Android Back notification logic. Model campaigns simulate progression; they do not replace a complete manual phone playthrough.

Native UI viewports include 360x640, 720x1280, 960x720 and 720x1600. Production/shop and legal tests use their own three-size sets. Store media consists of a 512x512 icon, 1024x500 feature graphic and four actual 1080x1920 English gameplay/title captures.

## Performance evidence and limits

Windows / Intel UHD / 720x1280 / normal real-time loop / 60 FPS cap. Five production/shop scenarios, each with 90 warm-up frames followed by 300 wall-time frame intervals, using staffed machinery, shoppers, vehicles and repair jobs. Maximum p95 across cases: **24.147 ms**; largest observed interval: **87.347 ms**; intervals above 33.333 ms: **3**. Static terrain, shadow and background rebuild counts stayed zero during measurements. Full samples and method are in `docs/release_qa/profile.json`.

These are finite Windows measurements. They do not establish Android/BlueStacks FPS, thermal behavior, startup speed or background lifecycle correctness. The user's earlier emulator frame-drop report requires device-specific retesting; it is not closed by a Windows benchmark.

## Android artifacts

The APK contains the full release-mode game with normal progression, audio and music. Development shortcuts and the funded test-yard tool are gated to editor/debug; use the editor's Settings for broad funded testing. The evaluation package installs separately from production, preserving the production application's independent data area. No personal save is bundled.

| Artifact | Details |
|---|---|
| `TrashEmpire-1.0.0.apk` | 119,360,813 bytes; `org.cardboardyard.empire.evaluation`; disposable evaluation signing certificate; do not publish |
| APK SHA-256 | `f3a3e679569e0d7bd2472a1c82cda7c1e873cc39045e44b71ae0bae5597a117c` |
| `TrashEmpire-1.0.0-unsigned-validation.aab` | 119,411,486 bytes; `org.cardboardyard.empire`; **unsigned**, build proof; generate a buyer-signed release |
| AAB SHA-256 | `75c69e21bc627ddf557cf6113ad38578026416108b88c8aa30b2384ff71254c6` |

Both have minimum API 24, target/compile API 36, versionCode 32 and ARMv7/ARM64/x86/x86_64. No Android permissions are requested; backup and debuggability are disabled. Official bundletool validates the AAB. APK signature and ZIP/native alignment are checked with Android build tools. Runtime language-name and policy JSON, gameplay data, translations and license texts match source bytes. Source-only tests, generators and reports are excluded from Android exports.

No device was attached to ADB during preparation. The independent Android matrix, including a 16 KB runtime and BlueStacks, remains **NOT RUN**; the separate user report is retained above. See `docs/release_qa/ANDROID_DEVICE_QA.md` for recording actual model, OS, settings and checksum.

## Licensing, privacy and publisher gates

Read `THIRD_PARTY_LICENSES.md`, `THIRD_PARTY_NOTICES.md`, `ASSET_INVENTORY.json` and retained license texts. Code, artwork, dialogue and original note-score music have Codex-assisted authorship. CC0 effects and OFL font retain their terms. The five mentor effects are procedural nonverbal synthesis, not recorded or cloned speech. GeneralUser GS sampled-instrument license limitations are disclosed; exclusive rights are not guaranteed by this report.

The game has no advertising, analytics, real-money purchases, account service or cloud saves. Progress and preferences are local. Publisher name, contact email, public HTTPS policy URL, audience, pricing and territories intentionally remain buyer fields. `tools/check_publisher.py` is expected to reject those templates until completed. Production signing, Play Console declarations/testing, rights review and device QA are required before submission. Current official policy links and the dated checklist are in `docs/PUBLISHING.md`.

## Evidence integrity

`docs/release_qa/verification.json` records results, artifact hashes, dates and coverage limits. `docs/release_qa/source-hashes.json` identifies tested runtime/assets/tools. `SOURCE_MANIFEST.json` covers every supplied source/document file; archive-level `ARTIFACTS.json` covers the APK and AAB. ZIP CRC and every listed file hash are verified during packaging.

Buyer logs preserve localized diagnostic output as reversible non-ASCII escape sequences to keep service files in English. Original UTF-8 log hashes and encoding notes are recorded in `verification.json`; original logs remain outside the deliverable. Escaping does not change pass/fail results. Historical reports are not relabeled as evidence for this candidate.

## Full regression result index

The following are the completed worktree group results. Inspect the associated logs for individual assertions.

| Group result | Checks |
|---|---:|
| source compilation checks | 307 |
| release readiness checks | 213 |
| yard feedback checks | 82 |
| mentor close checks | 60 |
| garden shadow checks | 33 |
| audio and large-control checks | 158 |
| map geometry checks | 601 |
| factory gameplay checks | 75 |
| bulky-find and shop checks | 124 |
| production clarity and live shop checks | 124 |
| precise collision and paving checks | 1612 |
| production and shop interface checks | 535 |
| marked map plan checks | 931 |
| restoring city background checks | 60 |
| marked map dialogue checks | 403 |
| functional building checks | 110 |
| building interface checks | 1534 |
| live building checks | 18 |
| building mentor checks | 31 |
| trolley animation checks | 36 |
| language resource checks | 68 |
| language selection checks | 270 |
| bulky-find interface checks | 610 |
| live factory runtime checks | 16 |
| factory interface checks | 724 |
| crew appearance checks | 15 |
| neighborhood gameplay checks | 125 |
| neighborhood interface checks | 3697 |
| enterprise simulation checks | 124 |
| enterprise interface checks | 703 |
| worker recovery checks | 62 |
| text layout checks | 2080 |
| district checks | 118 |
| district interface checks | 106 |
| marker/test-save checks | 93 |
| guidance checks | 390 |
| visual menu checks | 207 |
| progression checks | 194 |
| progression UI checks | 85 |
| workplace checks | 34 |
| yard polish checks | 105 |
| visual/lighting checks | 263 |
| title motion and object identity checks | 35 |
| menu and mentor redesign checks | 242 |
| facility foundation checks | 148 |
| integrated facility checks | 108 |
| new feature tutorial checks | 41 |
| facility UI/localization checks | 91 |
| machine level checks | 32 |
| facility cache checks | 9 |
| mentor opening checks | 34 |
| mentor cart checks | 18 |
| mentor feature checks | 79 |
| mentor resume/localization checks | 119 |
| guided layout checks | 502 |
| business checks | 28 |
| delivery checks | 98 |
| parking correction checks | 136 |
| parking geometry checks | 54 |
| cart regression checks | 11 |
| reliability checks | 60 |
| parking control checks | 19 |
| camera/control checks | 240 |
| contextual UI checks | 21 |
| campaign checks | 89 |
| scene checks | 24 |
| redesign checks | 26 |
| localization checks | 164 |
| expansion checks | 47 |
| expansion scene checks | 24 |
| background save checks | 7 |
| site geometry checks | 7 |
| space save checks | 23 |
| authoritative yard checks | 108 |
| movement/traffic checks | 54 |
| environment traffic checks | 27 |
