# home-hub-releases

Public release channel for **Home Hub** (the app code lives in the private
`Stevo238/home-hub` repo). Holds only:

- `version.json` — the update manifest the running app polls
- Release assets — `HomeHub.exe` attached to each `vX.Y.Z` release

The deployed app (on the Vienna server, `HUB_AUTO_UPDATE=1`) checks
`version.json` every 6 hours and, if `version` is newer than what it's
running, downloads the release EXE and restarts itself.

## Publishing a new version

1. In the code repo: bump `APP_VERSION` in `app.py`, rebuild `HomeHub.exe`.
2. `gh release create vX.Y.Z HomeHub.exe --repo Stevo238/home-hub-releases`
3. Update `version.json` here (version + url + notes) and push.
