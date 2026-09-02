# JuraSauria client releases

This repository hosts signed, credential-free JuraSauria update packages. Application source remains private.

## Publish an update

1. Open [Actions → Build client release](https://github.com/CynGames/jurasauria-releases/actions/workflows/release-client.yml).
2. Click **Run workflow**.
3. Enter a numeric version newer than the installed client (for example `32` or `32.1`).
4. Add short release notes and run it.

The workflow checks out the private source with a read-only deploy key, runs tests and linters, builds the Windows portable update, verifies that no `.env` is present, signs the update manifest, and publishes a GitHub Release.

Clients verify the Ed25519 signature, archive size, and SHA-256 checksum before installing. Client `.env`, data, database, and downloads are preserved.