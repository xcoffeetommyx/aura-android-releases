# Verify an Aura APK

Use the release's APK filename and SHA256SUMS. For example:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath '.\Aura-Music-Player-v<VERSION>.apk'
```

On Linux, put the APK and checksum file in the same directory and run
`sha256sum --check SHA256SUMS`. Obtain the expected checksum through the official
GitHub release/metadata record. A checksum alone cannot authenticate a compromised
publisher or an arbitrary mirror.

With Android SDK Build Tools installed:

```text
apksigner verify --verbose --print-certs Aura-Music-Player-v<VERSION>.apk
```

The maintained APK signer SHA-256 is:

```text
d73b50c33e022446320b2961283cd3ba727ec1c8948e94cea96cd5365fb64c9b
```

The package ID is `com.tommy.auraandroid`. The public version name and monotonically
increasing version code are in the release provenance. Android also verifies the
signature during installation; a matching package name alone is insufficient.
Preserve installed app data and use an in-place update. Never clear data or
uninstall to work around a signature mismatch.

APK signature verification is separate from a build attestation. These locally
signed releases do not claim an independent reproducible build or GitHub/OIDC
build attestation.
