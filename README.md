# Aura Music Player

Aura Music Player is a **closed-source Android application** distributed as signed
APK releases. Android application source is not published in this repository.

## Download

Open **[GitHub Releases](https://github.com/xcoffeetommyx/aura-android-releases/releases)**
and select the newest appropriate release. Expand **Assets** and download the
`Aura-Music-Player-v<VERSION>.apk`, `SHA256SUMS` and release provenance file.
Official Aura APKs are distributed through this repository's GitHub Releases.
GitHub's automatic source ZIP/tar downloads contain only this distribution
repository's documentation/metadata; they are not the app or its source code.

The initial channel is beta. GitHub does not designate prereleases as its stable
“Latest release,” so the Releases listing above is the permanent download link.
Once a stable release exists, `/releases/latest` will select that stable release;
it is not a reliable newest-beta link.

## Requirements and capabilities

Android 8.0 (API 26) or newer. See each release's metadata for its ABI inventory
and qualified device scope. Embedded Tailcat requires ARM64 or x86_64;
32-bit native entries from other libraries do not imply 32-bit Tailcat support. Physical ARM64 acceptance includes Samsung Galaxy
S23+; device-specific beta qualifications are described in the release notes.

Aura supports local music and optional self-hosted library access, streaming,
downloads/offline playback and Sessions. Cast requires a receiver-accessible
source; a phone-only Tailcat route is not a generic Cast proxy. Android Auto and
Cast retain their documented beta/device qualification limits.

[Aura Server](https://github.com/xcoffeetommyx/aura-server) is **open source and
self-hosted**. Your server hosts your music and accounts. Its networking/setup
requirements are documented there. Local playback does not require Aura Server.
This APK channel makes no Play Store availability claim.

## Install or update

1. Download the signed APK and compare its SHA-256 with the release record.
2. Android may ask you to allow installation from the browser/file manager you
   used. Enable that permission only for this installation, then disable it again.
3. Open the APK and install/update Aura. **Update the existing app in place** to
   preserve accounts, pairing and downloads; do not uninstall or clear app data.
4. If Android rejects the signature or downgrade, stop and check the official
   release metadata. Do not uninstall to bypass a compatibility error.

Checksums detect changed bytes; the APK signing certificate establishes update
continuity. Use this exact official repository, not a checksum from an unknown
mirror. [Verification instructions](VERIFYING.md) include the expected signer.

Compiled APKs can be inspected or decompiled. Existing R8 minification is not a
strong secrecy guarantee and is not a place to hide credentials.

[Distribution notice](DISTRIBUTION.md) · [Maintainer publication workflow](PUBLISHING.md)
