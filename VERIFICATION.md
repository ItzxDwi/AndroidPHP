# Verifying release artifacts

This project uses [Sigstore Cosign](https://github.com/sigstore/cosign) to sign release files. This verify that the files haven't been tempered with and are officially from this project

## Manual verification steps

1. Download Cosign

```bash
curl -sSLf https://github.com/sigstore/cosign/releases/latest/download/cosign-linux-amd64 -o cosign
chmod +x cosign
```

2. Verify signature

```bash
./cosign verify-blob \
  --signature checksums.sig \
  --certificate checksums.cert \
  checksums.sha256
```

3. Check checksums

```bash
sha256sum -c checksums.sha256
```

## What these files are

 * checksums.sha256: These are like digital fingerprints for release files, theymake sure nothing was changed.
 * checksums.sig: This is a signature that proves the files are authentic and haven't been tampered with.
 * checksums.cert: This certificate confirms that these files are sitned bu this build workflow, verifying its legitimacy.

## Why verify?

Verifying ensures that:

 * The release files are safe and unchanged since they were signed.
 * The signature confirms they originated from this repository's build workflow.
 * You are sure that you're running the exact binaries that were published and tested.
