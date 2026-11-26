# Plees-tracker Dev: Fixes, Features & Test Builds

Daily-driver fork of Miklos Vajna's ([`@vmiklos`](https://github.com/vmiklos)) [**Plees-tracker**](https://github.com/vmiklos/plees-tracker) targeting open issues and feature requests not yet addressed in the official build.

Every fix (`fix/*`) and feature (`feat/*`) lives on its own clean branch off `upstream/master` so it can be sent upstream as a pull request and dropped once it lands in the official app.

### How This Repo Is Organized

- **`master` mirrors [`vmiklos/plees-tracker:master`](https://github.com/vmiklos/plees-tracker) 1:1.** I never commit directly to `master` on GitHub so the default branch always stays even with upstream.
- **One issue or feature = one branch (`fix/*` or `feat/*`).** Every branch starts cleanly from `upstream/master` so it is easy to review or cherry-pick on its own.
- **Side-by-side `Plees-tracker Dev` APK ([Releases](https://github.com/TerribleTurtle/plees-tracker/releases)).** The `dev-ota` branch merges all active `fix/*` and `feat/*` branches on top of `upstream/master` and builds a signed `Plees-tracker Dev` (`hu.vmiklos.plees_tracker`) APK for `arm64-v8a`. Because it uses the `.dev` package ID, it installs right alongside the official Plees-tracker app without overwriting your main install.

---

## Active Branches (`0` Active, `1` Merged Upstream)

### 1. Open Upstream Pull Requests

| Issue | Branch & Diff | Upstream PR | Summary |
|---|---|---|---|

---

### 2. Staged Branches (Live on This Fork, Queued for Upstream PRs)

To avoid overwhelming the upstream PR queue, I keep these staged on their own branches until open PRs are reviewed. Each branch is rebased cleanly on `upstream/master` and can be cherry-picked independently:

| Issue | Branch & Diff | Status | Summary |
|---|---|---|---|

---

### 3. Previously Merged Upstream

| Issue | Branch | Upstream PR | Summary |
|---|---|---|---|
| [#510](https://github.com/vmiklos/plees-tracker/issues/510) | `fix/calendar-export-dedup` ([`93826602`](https://github.com/vmiklos/plees-tracker/commit/93826602)) | [**PR #649**](https://github.com/vmiklos/plees-tracker/pull/649) *(Merged)* | Deduplicate calendar exports and imports by whole-second start/stop timestamps and align exported calendar timestamps to whole seconds. |

---

## Using the `Plees-tracker Dev` Test APK ([Releases](https://github.com/TerribleTurtle/plees-tracker/releases))

If you are running into one of the issues listed above or want to try an unmerged feature before it lands in an official Plees-tracker release:

1. Grab the latest `Plees-tracker Dev` APK from [**Releases**](https://github.com/TerribleTurtle/plees-tracker/releases) (or point [Obtainium](https://github.com/ImranR98/Obtainium) at `https://github.com/TerribleTurtle/plees-tracker`).
2. It installs as **Plees-tracker Dev** (`hu.vmiklos.plees_tracker`) alongside the official Plees-tracker app so your normal setup stays untouched.
3. Each release is built automatically by GitHub Actions from [`dev-ota`](https://github.com/TerribleTurtle/plees-tracker/tree/dev-ota), which is simply `upstream/master` (`26.8.2`) plus the 0 active branches listed above.
4. **Please don't bug vmiklos with issues specific to this test build** - if you notice something odd while using `Plees-tracker Dev`, double-check whether it also happens on the official release from [`vmiklos/plees-tracker`](https://github.com/vmiklos/plees-tracker/releases) before opening an upstream issue.
