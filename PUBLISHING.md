# Maintainer release procedure

The application source checkout and signing credentials stay private. This public
repository receives only reviewed distribution documentation and non-secret
metadata. Do not add the private repository as a subtree, mirror or source ZIP.

1. Inspect the private source revision, installed version and previous releases.
   Choose the public version and a versionCode strictly above every distributed
   build. Public beta1 maps old internal 1.0/code 100 to 0.1.0-beta.1/code 101.
2. Commit only the intended private version/release changes. Build ordinary
   `:app:assembleRelease` locally, with existing R8/resource shrinking and the
   established production key. Never pass signing passwords on the command line.
   Never select proof, debug, androidTest, private-PKI or personal endpoint overrides.
3. Run affected tests. Inspect the APK manifest, ABI/native provenance, signature,
   ZIP contents and strings for debug/test artifacts, local paths and secrets.
   Audit licensing/notices without copying application source to this repository.
4. Compare the signer with the installed acceptance device. Use `adb install -r`
   and verify account/pairing/download continuity plus remote/offline playback.
   A signature/version mismatch blocks publication; never uninstall around it.
5. Copy only the reviewed APK to private release staging, rename it unambiguously,
   and generate checksum/provenance/notices. Review an explicit asset allowlist.
6. Commit this repository's metadata, tag the release, and publish the prerelease
   with the signed APK and reviewed metadata assets. Do not use wildcard uploads
   from a private build/evidence directory. Do not move a published tag or replace
   its APK with different bytes; publish a new version/code instead.
7. Download the public APK back from GitHub. Verify hash, APK signer, package and
   version again, install that downloaded file in place and repeat the small
   physical smoke including offline/process restart.
8. Confirm the application source repository remains private and this repository's
   complete history contains no application code or signing material. Record the
   result privately and keep only non-sensitive release metadata here.

There is intentionally no GitHub signing workflow. Automating signing requires a
separately reviewed credential design. Public source-commit hashes identify the
private producer revision without making the source publicly available.
