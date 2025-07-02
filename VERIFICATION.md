# Verifying release artifacts

All of the release files were signed using [Sigstore Cosign](https://github.com/sigstore/cosign), ensuring that they are genuine and unchanged since release.

## Verification steps

### 1. Install Cosign

#### Linux

```bash
curl -sSLf https://github.com/sigstore/cosign/releases/latest/download/cosign-linux-amd64 -o cosign
chmod +x cosign
```

#### macOS

```bash
curl -sSLf https://github.com/sigstore/cosign/releases/latest/download/cosign-darwin-amd64 -o cosign
chmod +x cosign
```
Or, if you use Homebrew:
```bash
brew install cosign
```

#### Windows (PowerShell)

```powershell
Invoke-WebRequest -Uri "https://github.com/sigstore/cosign/releases/latest/download/cosign-windows-amd64.exe" -OutFile "cosign.exe"
```

### 2. Download the required files
Download all of these files from the release page:

 * php
 * php.ini
 * php-android-pm5-latest.zip
 * php-android-pm5-latest.tar.gz
 * checksums.sha256
 * checksums.sig
 * checksums.pem

### 3. Check the signature

- On **Linux/macOS**:
    ```bash
    ./cosign verify-blob \
      --signature checksums.sig \
      --certificate checksums.pem \
      checksums.sha256
    ```

- On **Windows** (PowerShell):
    ```powershell
    .\cosign.exe verify-blob `
      --signature checksums.sig `
      --certificate checksums.pem `
      checksums.sha256
    ```

### 4. Verify checksums

- On **Linux/macOS**:
    ```bash
    sha256sum -c checksums.sha256
    ```
- On **Windows** (Git Bash):
    ```bash
    sha256sum -c checksums.sha256
    ```
- On **Windows** (PowerShell):
   ```powershell
   Get-FileHash -Algorithm SHA256 -Path (Get-ChildItem -Include *php*) | Format-List
   ```
   Then manually compare with checksums.sha256

## What these files are

 * **checksums.sha256**: These are like digital fingerprints, they make sure nothing was changed since release.
 * **checksums.sig**: This is a signature that verifies the files are genuine and unchanged.
 * **checksums.pem**: This certificate confirms that these files were signed by this build workflow.

## Why verify?

* Keeps files safe and unchanged since release, preventing malicious changes.
