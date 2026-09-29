# Covai-Labs Homebrew Tap

Homebrew tap for [JobFoundry](https://github.com/Covai-Labs/JobFoundry) — local-first job search pipeline.

## Status

Tap shell is live. The formula is **pending the first macOS tarball release**: `v0.4.0` ships no `*-darwin-arm64.tar.gz` asset yet, and `Formula/jobfoundry.rb` still carries a `REPLACE_WITH_DARWIN_ARM64_SHA256` placeholder. Do not advertise `brew install` as working until the placeholder is filled from a published `.sha256` sidecar and tested on a Mac.

## Fill the formula on release

1. Cut a release with a `jobfoundry-<version>-darwin-arm64.tar.gz` + `.sha256` asset (see `packaging/homebrew/README.md` in JobFoundry).
2. Update `Formula/jobfoundry.rb`: `version`, `url`, `sha256`.
3. Test on a Mac:
   ```bash
   brew tap covai-labs/tap
   brew install --build-from-source covai-labs/tap/jobfoundry
   brew audit --strict covai-labs/tap/jobfoundry
   brew test covai-labs/tap/jobfoundry
   jobfoundry status
   ```

## Install (once formula is filled)

```bash
brew install covai-labs/tap/jobfoundry
jobfoundry status
jobfoundry start
brew services start jobfoundry
```
