> Public showcase copy of game handover documentation. Game-source paths, JSON manifests, tests and build artifacts mentioned below refer to the separate private buyer package. They are not included in this public repository. Original report dates are retained.

# TRASH EMPIRE known issues and release gates

Version 1.0.0 / Android versionCode 32. Status and reproducible evidence are in `QA_REPORT_FULL.md` and `docs/release_qa/verification.json`. This file distinguishes tested behavior from work that requires the buyer's environment.

| ID | Status / impact | Required action |
|---|---|---|
| DEVICE-01 | Seller/user reports normal Android operation; model, OS and tested build checksum were not supplied. The new 1.0.0 evaluation APK and BlueStacks have no independently recorded device run. Windows native timings do not predict emulator performance. | Complete the device matrix in `docs/release_qa/ANDROID_DEVICE_QA.md`, including worker recovery and frame-drop scenarios. Record actual devices and results. |
| DEVICE-02 | Static AAB checks establish API/ABI/16 KB packaging compatibility; no 16 KB device/emulator run has been performed. | Test the signed release in a 16 KB Android environment. |
| PERF-01 | The finite Windows profile recorded three intervals above 33.333 ms among 1,500 measured frames, all in the parking case; maximum 87.347 ms. No static geometry rebuilds occurred. | Inspect target-device frame times and worker/vehicle workloads before promising a constant 60 FPS. Full measurements are retained in the QA report. |
| PUBLISHER-01 | Publisher identity, support email, privacy URL, audience, pricing and territories are intentionally buyer fields. The metadata checker should fail until completed. | Fill the templates, host the policy and complete Play Console declarations. |
| SIGNING-01 | The AAB is unsigned validation output. The evaluation APK has a disposable evaluation certificate and separate package id. | Build a fresh production AAB with the buyer's upload key. Do not publish the evaluation application. |
| LANGUAGE-01 | All 11 languages have automated catalog, glyph and selected UI-fit checks. Independent native-speaker review of every string is incomplete. | Review translations and real-device wrapping, prioritizing English. Ukrainian remains a selectable translation. |
| RIGHTS-01 | Original project code, art, dialogue and music have Codex-assisted authorship. Third-party material cannot be transferred as exclusive original work. GeneralUser GS retains historical sample-origin limitations. | Assess retained terms and define rights in the sale agreement; replace music if stronger provenance is required. |
| SERVICES-01 | The game currently has no ads, IAP, analytics, account service or cloud saves. | Adding a service requires implementation, privacy updates and new device QA. |

No unresolved gameplay failure is asserted to be absent merely because an automated suite passes. Test results cover the specified inputs, resolutions and simulated progression; they do not establish an exhaustive visual audit or store acceptance. Any new reproducible problem should be recorded with build checksum, save, device, steps and expected/actual behavior.

Historical bugs fixed during development include blocked worker reservations, overlapping interaction zones, mentor close handling, scroll input, text overflow and save-backup recovery. Current regressions cover these paths; device confirmation remains part of DEVICE-01.
