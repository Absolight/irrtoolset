# Maintainer: Mathieu Arnold <mat@FreeBSD.org>

pkgname=irrtoolset
pkgver=5.1.3
pkgrel=1
pkgdesc="Suite of tools to operate with routing policies in RPSL format."
arch=('x86_64')
url="https://github.com/irrtoolset/irrtoolset/"
license=('custom')
depends=('readline' 'gcc-libs')
makedepends=('gcc' 'libtool' 'flex' 'bison')
source=("https://github.com/irrtoolset/irrtoolset/archive/release-$pkgver.tar.gz")
sha256sums=("a3eff14c2574f21be5b83302549d1582e509222d05f7dd8e5b68032ff6f5874a")

build() {
  cd "${srcdir}/${pkgname}-release-${pkgver}"

  autoreconf -i
  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-release-${pkgver}"

  make DESTDIR="$pkgdir/" install
  mkdir -p "${pkgdir}/usr/share/licenses/${pkgname}"
  cp COPYING "${pkgdir}/usr/share/licenses/${pkgname}/"
}
