# Vira media library

Pose videos and music for the Vira Android app (version 1.0.3).

The app downloads these files anonymously from the assets of the **media-v2**
release (Releases tab), in the form `pose-<id>.mp4`, `track-<n>.mp3`, plus
`manifest.json`. Do not add media files to the repository itself.

## Notes

* The library totals 605,113,590 bytes (67 pose videos, 15 music tracks).
* The app verifies every download against the size and SHA-256 in the manifest
  bundled inside the APK, so downloads are safe to resume or retry.
* The authoritative manifest ships inside the APK
  (`assets/media_manifest.json`). The `manifest.json` asset in the media-v2
  release was generated just before the release tag was renamed from media-v1
  to media-v2, so its `baseUrl` field still says `media-v1`; every file URL
  under media-v2 works, and the app does not read that remote copy.
* Releases here are immutable: a tag used by a published release can never be
  reused. Publish a new tag for a new library revision and update the base URL
  in the app build.