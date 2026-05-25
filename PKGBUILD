# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-frameworks-windowsystem
pkgver=6.26.0
pkgrel=2
pkgdesc='Access to the windowing system for Artix Linux'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-frameworks-windowsystem'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(glibc
         libgcc
         libx11
         libxcb
         libxfixes
         qt6-base
         xcb-util-keysyms)
makedepends=(doxygen
             extra-cmake-modules
             qt6-declarative
             qt6-tools)
optdepends=('qt6-declarative: QML bindings')
groups=(sonicde-frameworks)
conflicts=('kwindowsystem')
replaces=('kwindowsystem')
provides=('kwindowsystem')
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('58a768b5da6916de9e13d02dae4eaa8aff99317b095a9b18306d0f3f162f47ad')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
