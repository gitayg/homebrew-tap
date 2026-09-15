# gitayg/homebrew-tap

Homebrew tap for [MoorAI](https://moorai.dev), which provides on-device guardrails for AI coding agents.

```bash
brew install --cask gitayg/tap/moorai
```

Homebrew only loads casks from third-party taps that you trust. Installing by the full name, as above, trusts only this cask. If you'd rather tap first and use the short name, run `brew tap gitayg/tap && brew trust --cask gitayg/tap/moorai`, then `brew install --cask moorai`.

| Cask | What it installs |
|---|---|
| `moorai` | MoorAI desktop app for macOS (Apple silicon) |

## Notes

- The cask downloads the signed and notarized DMG from `https://moorai.glick.run/download/app`. That URL always points at the latest build, so the cask uses `version :latest` and `sha256 :no_check`.
- The app updates itself, and the cask declares `auto_updates true`. Use `brew upgrade --cask --greedy moorai` to force a reinstall.
- `brew uninstall --cask moorai` keeps your settings. `brew uninstall --zap --cask moorai` also deletes MoorAI's config and state directories.

## Maintaining

The source of truth is `packaging/homebrew/moorai.rb` in [gitayg/moorai](https://github.com/gitayg/moorai). Copy changes here from that file. Because the cask doesn't pin a version or checksum, a normal release needs no update here.
