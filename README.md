Package wrapper for various packages I contribute to. Individual instructions below

Subtree maintenance is managed with a `aurpublish`

For usage: `aurpublish --help` or `aurpublish -h`

Credit to https://github.com/yuvadm/archlinux-packages for the original maintenance script that led me to aurpublish

# Heroku CLI
heroku-cli is downloaded, compiled and hosted on google storage using a simple set of commands

### to compile the cli:

1. if updating to a new version, set the package version by updating `VERSION` in `bin/compile_heroku_cli`
2. set the release number of the package version by updating `RELEASE` in `bin/compile_heroku_cli`
3. run the compiler
    ```bash
    bin/compile_heroku_cli
    ```
    - Check sums, pkgver and pkgrel will all be automatically updated in `heroku-cli/PKGBUILD`
    - verify that `makepkg` succeeds
4. test by installing locally
    ```bash
    cd heroku-cli
    # where "VERSION" is the pkgver and RELEASE is the pkgrel
    sudo pacman -U heroku-cli-VERSION-RELEASE-any.pkg.tar.zst
    ```
