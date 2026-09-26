# IconGrabber (HOS 22.5.0 fix)

Fork of [Slluxx/IconGrabber](https://github.com/Slluxx/IconGrabber), a homebrew app for the Nintendo Switch that grabs custom icons from SteamGridDB. The original repo is archived and stopped working on newer firmware (HOS 21.0.0+).

## What's fixed

- Game list used to stop completely if a single installed title failed to load its control data. Now it just skips that title and keeps going.
- Added basic curl SSL/timeout settings — requests could silently fail depending on the console's clock/cert store.
- Wrapped JSON parsing in a try/catch so a bad API response doesn't crash the whole app.
- Small null-check fix for the icon "lock" field.


## Building

Needs devkitPro (devkitA64 + libnx) with these portlibs installed:

```
pacman -S switch-curl switch-mbedtls switch-zlib switch-glfw switch-mesa switch-libdrm_nouveau switch-glm
```

Then:

```
make
```

## Download

Prebuilt `.nro` is on the [Releases](../../releases) page.
