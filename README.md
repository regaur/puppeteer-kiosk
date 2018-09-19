puppeteer-kiosk
===
> Launch puppeteer in auto-login session

# Usage

Set environment variable `kiosk_url` in a script in in `~auto_login/x.session.d` that sorts before `50-`. If none is set, a nice interactive particle effect is shown. (requires Internet)


This repository containes sources of an Arch Linux (pacman) package, see [PKGBUILD](https://wiki.archlinux.org/index.php/PKGBUILD) for details. Being opinionated and special-purpose, it is not published on the AUR (Arch User Repository), but instead is part of a [collection of atomic configuration snippets](https://github.com/regaur) I use to build Arch-based systems.

Build
---

```
makepkg --sign
```

See Also
---

- [ssb-pacman](https://github.com/regular/ssb-pacman)
- [ssb-archiso](https://github.com/regular/ssb-archiso)
