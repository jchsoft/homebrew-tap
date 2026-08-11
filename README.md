# homebrew-tap

Homebrew tap for JCHSoft tools.

```bash
brew install jchsoft/tap/mcptask_runner
```

`brew tap jchsoft/tap` looks for this repository — the `homebrew-` prefix is
Homebrew's convention, not part of the tap's name.

## What is in here

| Cask | What it is |
| --- | --- |
| `mcptask_runner` | the [mcptask](https://mcptask.online) runner — drives Claude Code through the tasks on mcptask.online |

A cask rather than a formula, because what is installed is a pre-built binary; a
formula describes something Homebrew builds from source. Casks are macOS-only —
on Linux, install with the script instead:

```bash
curl -fsSL https://github.com/jchsoft/mcptask-releases/releases/latest/download/install.sh | sh
```

## Do not edit `Casks/`

Every file under `Casks/` is generated and pushed by
[goreleaser](https://goreleaser.com) when a release is cut, and an edit here is
overwritten by the next one. The cask's contents — its version, its URLs, its
checksums, its post-install hook — come from `.goreleaser.yaml` in the (private)
source repository. The binaries themselves live in
[jchsoft/mcptask-releases](https://github.com/jchsoft/mcptask-releases).

The cask clears `com.apple.quarantine` after installing. The binaries are not
code-signed, and without that the first run dies with "cannot be opened because
the developer cannot be verified" — no output and no explanation. It is
Homebrew's documented answer for unsigned binaries.

---

Proprietary — © JCHSoft. All rights reserved.
