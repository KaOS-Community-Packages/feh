pkgname=feh
pkgver=3.10.3
pkgrel=1
pkgdesc='Fast and light imlib2-based image viewer'
url='http://feh.finalrewind.org/'
license=('custom:MIT')
arch=('x86_64')
depends=('imlib2' 'curl' 'libxinerama' 'libexif' 'libpng' 'imagemagick' 'file')
makedepends=('libxt' 'clang')
source=("${url}${pkgname}-${pkgver}.tar.bz2")
sha1sums=('62702c99a2d30b01c20421e71233b7d9649ff74d')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make CC=clang PREFIX=/usr exif=1 help=1 stat64=1 magic=1
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install

	install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
