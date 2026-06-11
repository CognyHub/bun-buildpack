# buildpack-bun

Heroku buildpack that installs the [Bun](https://bun.sh) runtime into the slug.

## Usage

```
heroku buildpacks:add https://github.com/CognyHub/buildpack-bun --app <app>
heroku config:set BUN_VERSION=1.2.3 --app <app>
```

If `BUN_VERSION` is not set, the latest release is resolved at build time.

## Caching

The binary is cached in `CACHE_DIR/bun-<version>/bun`. Changing `BUN_VERSION`
automatically invalidates the cache and triggers a fresh download.

## Platform

Targets `heroku-26` (linux/amd64). The asset `bun-linux-x64.zip` is always used.
