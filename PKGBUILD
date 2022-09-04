#!/bin/bash

# Created from the original PKGBUILD by Daniel Peukert <dan.peukert@gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/fontfinder/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/fontfinder/discussions>

pkgname="google-font-download"
pkgver="1.4.3"
pkgrel="1"
pkgdesc="Google Fonts web font downloader"
arch=(
  "any"
)
url="https://github.com/neverpanic/$pkgname"
license=(
  "BSD"
)
depends=(
  "curl"
  "ncurses"
)
checkdepends=(
  "xxd"
)
source=(
  "$pkgname-$pkgver-$pkgrel.tar.gz::$url/archive/$pkgver.tar.gz"
)
sha512sums=(
  "30c9731bdbc31162ec1ace4dcd2fa08245d39c4acd275942f22d018b15593f92"
)

_sourcedirectory="$pkgname-$pkgver"

check() {

  cd "$srcdir/$_sourcedirectory/"

  make syntax-check

  make test
}

package() {

  cd "$srcdir/$_sourcedirectory/"

  install -Dm755 "$pkgname" "$pkgdir/usr/bin/$pkgname"

  install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
