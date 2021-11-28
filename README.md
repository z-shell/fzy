<h3>

| **Package source:** |           Tarball            | Binary |        Git         | Node | Gem |
| :-----------------: | :--------------------------: | :----: | :----------------: | :--: | :-: |
|     **Status:**     | :heavy_check_mark: (default) |  :x:   | :heavy_check_mark: | :x:  | :x: |

</h3>

- [Introduction](#introduction)
- [Install](#install)
	- [Available `pack''` invocations](#available-pack-invocations)
- [Default Profile](#default-profile)
- [`Bin-Gem-Node` Profile](#bin-gem-node-profile)

# Introduction

> **[?]**
> This repository not compatible with previous versions (zplugin, zinit).
>
> Please upgrade to [ZI](https://github.com/z-shell-zi)

The [jhawthorn/fzy](https://github.com/jhawthorn/fzy) zsh package than can use the NPM package registry to automatically:

-   get the plugin's Git repository OR release-package URL,
-   get the list of the recommended ices for the plugin,
    -   there can be multiple lists of ices,
    -   the ice lists are stored in _profiles_; there's at least one profile, _default_,
    -   the ices can be selectively overridden.

# Install

## Available `pack''` invocations

```zsh
# Download the package with the default ice list
zi pack for fzy

# Download the package with the bin-gem-node annex-utilizing ice list
zi pack"bgn" for fzy

# Download with the bin-gem-node annex-utilizing ice list FROM GIT REPOSITORY
zi pack"bgn" git for fzy

# Download normal ice list and override atclone'' ice to skip the contrib scripts
zi pack"bgn" atclone'' for fzy
```

# Default Profile

Provides the fuzzy finder via Makefile-installation of the `fzy` binary under `$ZPFX/bin`.

```zsh
zi lucid as"program" pick"$ZPFX/bin/fzy*" \
    atclone"cp contrib/fzy-* $ZPFX/bin" \
    make"PREFIX=$ZPFX install" \
    …
```

# `Bin-Gem-Node` Profile

Provides the fuzzy finder via _shims_, i.e.: automatic forwarder scripts created under `$ZPFX/bin` (which is added to the `$PATH` by default).
It needs the [bin-gem-node](https://github.com/z-shell/z-a-bin-gem-node) annex.

```zsh
zi lucid as"null" make sbin"fzy;contrib/fzy-*" …
```
