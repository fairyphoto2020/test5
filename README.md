# closed

Generated Android Trusted Web Activity (TWA) project for **closed**.

![App icon](app/src/main/ic_launcher-playstore.png)

## Project Summary

| Field | Value |
| --- | --- |
| App name | closed |
| Short name | ctg |
| Package ID | `co.gjjj.jj` |
| Website URL | https://www.closedtesthelp.com/twa/ |
| Verified host | closedtesthelp.com |
| Description | Seamless Access to Services & Products |
| Generated at | 2026-05-19 04:58:59 UTC |

## What This Project Contains

- Native Android wrapper for your website using Trusted Web Activity.
- App launcher icons generated from the uploaded logo.
- Manifest, strings, package ID, and TWA config updated from the builder form.
- GitHub Actions workflow to build signed release APK and Play Store AAB artifacts.
- Default keystore for immediate test builds.
- Optional production keystore support through GitHub Actions secrets.

## Download APK and AAB From GitHub Actions

1. Open this repository on GitHub.
2. Go to the **Actions** tab.
3. Open the latest **Build Android TWA (APK & AAB)** workflow run.
4. Download the artifacts:
   - `TWA-Release-APK` for direct APK testing.
   - `TWA-Release-AAB` for Google Play Console upload.

## Signing Details

This project can build immediately with the included default keystore:

| Setting | Value |
| --- | --- |
| Keystore file | `app/keystore/keystore.jks` |
| Store password | `androidpassword` |
| Key alias | `myalias` |
| Key password | `androidpassword` |

For production Play Store releases, use your own private keystore by adding these GitHub repository secrets:

- `JKS_BASE64`
- `KEYSTORE_PASSWORD`
- `KEY_ALIAS`
- `KEY_PASSWORD`

The GitHub workflow automatically uses those secrets when they are present. If they are missing, it falls back to the default keystore so users can still generate APK and AAB files.

## Domain Verification

To hide the browser toolbar and complete TWA verification, upload an `assetlinks.json` file to:

```text
https://closedtesthelp.com/.well-known/assetlinks.json
```

Use the package ID above and the SHA-256 fingerprint from Google Play Console or Android Studio.

## Local Build Commands

```bash
./gradlew assembleRelease
./gradlew bundleRelease
```

Build outputs:

- APK: `app/build/outputs/apk/release/app-release.apk`
- AAB: `app/build/outputs/bundle/release/app-release.aab`
