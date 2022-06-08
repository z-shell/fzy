<div align="center">
<h1><a href="https://github.com/z-shell/zi">
  <img src="https://github.com/z-shell/zi/raw/main/docs/images/logo.svg" alt="Logo" width="60px" height="60px" /></a>
    ❮ ZI ❯ Package - Fzy </h1>
<h3 align="center">

| **Package source:** |           Tarball            | Binary |        Git         | Node | Gem |
| :-----------------: | :--------------------------: | :----: | :----------------: | :--: | :-: |
|     **Status:**     | :heavy_check_mark: (default) |  :x:   | :heavy_check_mark: | :x:  | :x: |

</h3></div><hr />

### Available `pack''` invocations

```shell
# Download the package with the default ice list
zi pack for fzy
```

```shell
# Download the package with the bin-gem-node annex-utilizing ice list
zi pack"bgn" for fzy
```

```shell
# Download with the bin-gem-node annex-utilizing ice list FROM GIT REPOSITORY
zi pack"bgn" git for fzy
```

```shell
# Download normal ice list and override atclone'' ice to skip the contrib scripts
zi pack"bgn" atclone'' for fzy
```

### Default Profile

Provides the fuzzy finder via Makefile-installation of the `fzy` binary under `$ZPFX/bin`.

```shell
zi lucid as"program" pick"$ZPFX/bin/fzy*" \
  atclone"cp contrib/fzy-* $ZPFX/bin" \
  make"PREFIX=$ZPFX install" \
    …
```

### `Bin-Gem-Node` Profile

Provides the fuzzy finder via _shims_, i.e.: automatic forwarder scripts created under `$ZPFX/bin` (which is added to the `$PATH` by default).
It needs the [bin-gem-node](https://github.com/z-shell/z-a-bin-gem-node) annex.

```shell
zi lucid as"null" make sbin"fzy;contrib/fzy-*" …
```

---

> This repository compatible with [ZI](https://github.com/z-shell/zi)

The [jhawthorn/fzy](https://github.com/jhawthorn/fzy) zsh package that can use the [zsh-string-lib](https://github.com/z-shell/zsh-string-lib) to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in _profiles_; there's at least one profile, _default_,
  - the ices can be selectively overridden.
