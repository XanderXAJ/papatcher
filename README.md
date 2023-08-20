# Planetary Annihilation Patcher

This is a forked version of [the official papatcher](https://github.com/planetary-annihilation/papatcher) that make a couple of changes to better support rootless container/Docker setups:

- Allow configuring the cache directory using `-cachedir`
- Only require a user to exist if either `-dir` or `-cachedir` are prefixed with `~` (home directory)
    - If `papatcher` fails because a user doesn't exist, specify exact paths for `-dir` and `-cachedir`

It also fixes a certificate issue when contacting PA services by instead relying on the OS certificate store.

## Installation

```shell
go install github.com/xanderxaj/papatcher@main
```

## Usage

```shell
$ papatcher -h
Usage of papatcher:
  -cachedir string
        Cache directory
  -dev
        Use PAnet dev environment
  -dir string
        Target directory to patch
  -password string

  -quiet
        No status updates
  -stream string
        Stream to download/update (default "stable")
  -update-only
        Only do an update, don't launch
  -username string

```
