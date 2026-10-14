# QR Scanner Pro Galaxy Remote Config

Exclusive package: `com.qrpro.scanner.gx`.
Manifest AdMob App ID: `ca-app-pub-3289974964220873~1766489685`.
Current revision: 3. Mode: off. Ads enabled: false. Production approval: false.

Revision 3 retains the five real units supplied in the owner's October 13, 2026
AdMob screenshot. They are not used for requests while advertising remains OFF.
The screenshot also lists banner `ca-app-pub-3289974964220873/2530287305`;
the app has no banner placement, so this unit is not configured.

Galaxy 1.0.1 (version code 2) is a non-debuggable Release build. It defaults to OFF
and rejects cached/remote test mode. Debug builds can never use production units.
Consent, Premium/trial/reward access, global/per-format switches and pacing still apply.
The first-install trial suppresses all ads, including test ads.

## Switch Later

Only after the exact Galaxy app is live and the owner explicitly requests production:

1. Confirm app registration and Privacy & messaging in AdMob.
2. Reconfirm the five staged unit IDs belonging to publisher `3289974964220873`.
3. Set `ad_mode` to `production` and `production_ads_approved` to true.
4. Set `ads_enabled` true, enable desired per-format switches, and increment `config_revision`.
5. Reopen the app to fetch the new config, then verify SDK requests and impressions.

No APK update is needed for a mode/unit change with this release. The manifest App ID
cannot change remotely. Wrong packages, unknown modes, unapproved production mode,
demo/placeholder/other-publisher production units fail closed.

Rollback: set `ads_enabled` false or `ad_mode` off, then increment config_revision.
Valid config is cached; failed fetches/malformed payloads retain last-known-good data.
Edits apply after a successful fetch on app startup, not instantly to every running app.

Use debug builds for demo validation, not the archived 1.0.0 test-ad Release APK.
Galaxy 1.0.1 hides purchases, trial and rewarded offers; batch scanning and CSV
are available without a purchase. Only compiled placements can be enabled remotely.
Do not treat this configuration as store approval or production-serving evidence:
https://developers.google.com/admob/android/test-ads

The older `qrscanner-pro-config` repository remains unchanged for older/Play builds.
Support/website fields are metadata; only links already consumed by the Android app
are applied automatically. Store purchases require completed Samsung IAP wiring
and a new release; remote configuration cannot add that implementation.
