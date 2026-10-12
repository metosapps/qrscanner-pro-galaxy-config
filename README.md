# QR Scanner Pro Galaxy Remote Config

Exclusive package: `com.qrpro.scanner.gx`.
Manifest AdMob App ID: `ca-app-pub-3289974964220873~1766489685`.
Current revision: 1. Mode: test. Production approval: false.

The Android artifact is a signed non-debuggable Release build. Ad mode is independent
of build type: test mode forces Google's five official demo units, even if an ID
field contains a production unit. Debug builds can never use production units.
Consent, Premium/trial/reward access, global/per-format switches and pacing still apply.
The first-install trial suppresses all ads, including test ads.

## Switch Later

Only after the exact Galaxy app is live and the owner explicitly requests production:

1. Confirm app registration and Privacy & messaging in AdMob.
2. Supply the five actual unit IDs belonging to publisher `3289974964220873`.
3. Set `ad_mode` to `production` and `production_ads_approved` to true.
4. Keep desired global/per-format switches enabled and increment `config_revision`.
5. Reopen the app to fetch the new config, then verify SDK requests and impressions.

No APK update is needed for a mode/unit change with this release. The manifest App ID
cannot change remotely. Wrong packages, unknown modes, unapproved production mode,
demo/placeholder/other-publisher production units fail closed.

Rollback: set `ads_enabled` false or `ad_mode` off, then increment config_revision.
Valid config is cached; failed fetches/malformed payloads retain last-known-good data.
Edits apply after a successful fetch on app startup, not instantly to every running app.

Use this test-mode Release APK for validation. Google's guidance says to replace demo
unit IDs before public publication, or use registered test devices with your own units.
Do not treat this configuration as store approval or production-serving evidence:
https://developers.google.com/admob/android/test-ads

The older `qrscanner-pro-config` repository remains unchanged for older/Play builds.
Support/website fields are metadata; only links already consumed by the Android app
are applied automatically. Store purchases still require completed Samsung IAP wiring.
