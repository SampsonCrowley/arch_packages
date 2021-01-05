Package wrapper for various packages I contribute to. Individual instructions below

Subtree maintenance is managed with `aurpublish`

For usage: `aurpublish --help` or `aurpublish -h`

Credit to https://github.com/yuvadm/archlinux-packages for the original maintenance script that led me to aurpublish

# Heroku CLI (bin)
heroku-cli-bin is downloaded, compiled and hosted through a github tag using a simple set of commands

### to compile the cli:

1. if updating to a new version, set the package version by updating `VERSION` in `.heroku-cli-bin-host/bin/compile`
2. set the release number of the package version by updating `RELEASE` in `.heroku-cli-bin-host/bin/compile`
3. run the compiler
    ```bash
    bin/compile_heroku_cli
    ```
    - Checksums, pkgver and pkgrel will all be automatically updated in `heroku-cli-bin/PKGBUILD`
    - verify that `makepkg` succeeds
4. test by installing locally
    ```bash
    cd heroku-cli-bin
    # where "VERSION" is the pkgver and RELEASE is the pkgrel
    sudo pacman -U heroku-cli-bin-VERSION-RELEASE-any.pkg.tar.zst
    ```
