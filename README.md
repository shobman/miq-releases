# miq-releases

**Build artifacts and the update manifest for [miq](https://github.com/shobman/miq). No source code.**

This repository exists for one reason: miq's source repo is private, and release assets on a private
repo need authentication to download. A miq server or player checking for an update must not have to
carry a credential — so the artifacts live here, public and unauthenticated, and the source stays
private.

## What is in here

- Release assets: the server package and the signed Fire TV APK, per tagged version.
- `manifest.json` — the small document a running miq reads to learn whether a newer version exists.

## What is NOT in here, ever

Source code, development notes, or anything else from the private repo. Publishing workflows
enumerate exactly what they upload; they never copy a directory.

## Verifying what you downloaded

The Fire TV APK is signed with a fixed release identity that will never change. Check it:

```sh
apksigner verify --print-certs miq-head-firetv.apk
```

A different signature means it did not come from us.
