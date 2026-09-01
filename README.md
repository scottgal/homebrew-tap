# scottgal/homebrew-tap

Homebrew tap for [mostlylucid](https://www.mostlylucid.net) applications.

## mylo

An RSS and Atom reader for the desktop. It runs on your machine, fetches feeds
directly from the sites that publish them, and keeps everything in one SQLite
file you own. No account, no server, no browser engine inside it.

```bash
brew install --cask scottgal/tap/mylo
```

Source, releases and the user manual:
[scottgal/lucidview](https://github.com/scottgal/lucidview).

### About the first launch

mylo is ad-hoc signed and not notarized with an Apple Developer ID. Homebrew
attaches `com.apple.quarantine` to everything it downloads, and macOS refuses
to open a quarantined app that is not notarized, reporting it as damaged. The
cask clears that attribute from the copy it installs, so the app opens
normally.

If you would rather make that call yourself, install with `--no-quarantine`
and the cask leaves the attribute alone for you to handle, or run:

```bash
xattr -dr com.apple.quarantine /Applications/mylo.app
```

### Updating the cask

The checksums here are generated, never typed. Each mylo release attaches a
finished `mylo.rb` built from the artifacts it just produced; copy that file
over `Casks/mylo.rb`. `packaging/homebrew/update-cask.sh` in the lucidview
repository rewrites it from any published tag.
