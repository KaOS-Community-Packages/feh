pkgname=feh
pkgver=2.20
pkgrel=1
pkgdesc='Fast and light imlib2-based image viewer'
url='http://feh.finalrewind.org/'
license=('custom:MIT')
arch=('x86_64')
depends=('giblib' 'curl' 'libxinerama' 'libexif' 'libpng' 'libx11' 'imagemagick')
makedepends=('libxt' 'clang')
source=("${url}${pkgname}-${pkgver}.tar.bz2")
sha1sums=('1a14f288b23e2e96d2b4b31d7f38736ee936c754')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make CC=clang PREFIX=/usr exif=1 help=1 stat64=1
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install

	install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	#chmod 644 "${pkgdir}/usr/share/icons/hicolor/"{48x48/apps/feh.png,scalable/apps/feh.svg}
}
