# Arch PKGBUILDs

This repository is composed of PKGBUILDs I have written for myself or maintain at some point (and
those are available at AUR).

## Adding a new AUR

```bash
$ pkgname=mycoolnewpkg
$ mkdir _$pkgname && cd _$pkgname
$ git init
$ git branch -M master
$ git remote add origin ssh://aur@aur.archlinux.org/$pkgname.git
$ touch PKGBUILD
```

Then do your thing, make sure it works with `makepkg -fsri` and finally:

```bash
$ makepkg --printsrcinfo > .SRCINFO
$ git add PKGBUILD .SRCINFO
$ git commit -m "feat: initial commit"
$ git push
$ xdg-open https://aur.archlinux.org/packages/$pkgname
```

Do your editing on the UI, now lets add it as a submodule to the enclosure repository.

```bash
$ cd ..
$ git remote add origin ssh://aur@aur.archlinux.org/$pkgname.git
$ rm -rf _$pkgname
```

## License

The contents of this repository are licensed under Apache v2.
