
# Maintainer: Dave Murphy <davem@devkitpro.org>

pkgname=('libnx-git')
_gitname=libnx
pkgver=v1.4.1.r50.bcddc1e
pkgrel=1
pkgdesc="Nintendo Switch AArch64-only userland library."
arch=('any')
license=('custom')
url="https://github.com/switchbrew"
options=(!strip libtool staticlibs)
source=(git+https://github.com/switchbrew/libnx.git)
#source=(git+${url}/${pkgname}.git)
#source=(${url}/${pkgname}/releases/download/v${pkgver}/${pkgname}-src-${pkgver}.tar.bz2)
#sha256sums=('e06595b8e9c2c81f7dbef209640f1803edd01a5f26db945b0eed912eb933c08e')
sha256sums=('SKIP')
makedepends=('devkitA64')
provides=('libnx')
conflicts=('libnx')

build() {

  make -C "$srcdir/$_gitname"

}

package() {

  make -C "$srcdir/$_gitname" DESTDIR=$pkgdir install

}

pkgver() {

  cd "$srcdir/$_gitname"
  printf "%s" "$(git describe --long | sed 's/\([^-]*-\)g/r\1/;s/-/./g')"

}
