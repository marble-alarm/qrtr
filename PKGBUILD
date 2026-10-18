# Maintainer: hiruocha <hiruocha[at]outlook[dot]com>
# Contributor: Super Tecno Gym <banana@grrlz.net>
# Contributor: Sam Day <me@samcday.com>

pkgname=qrtr
pkgver=1.2
pkgrel=1
pkgdesc="Userspace reference for net/qrtr in the Linux kernel"
arch=('aarch64')
url="https://github.com/linux-msm/qrtr"
license=('BSD-3-Clause')
makedepends=('meson')

source=("$pkgname-$pkgver.tar.gz::$url/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('7a82bf80246fe71287b13c66c0466208822e8337fcd4aaf302eee6c5fcb48a52')

build() {
  cd "$pkgname-$pkgver"
  arch-meson . build
  meson compile -C build
}

package() {
  cd "$pkgname-$pkgver"
  DESTDIR="$pkgdir" meson install --no-rebuild -C build
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
