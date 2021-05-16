pkgname=feh
pkgver=3.7
pkgrel=1
pkgdesc='Fast and light imlib2-based image viewer'
url='http://feh.finalrewind.org/'
license=('custom:MIT')
arch=('x86_64')
depends=('giblib' 'curl' 'libxinerama' 'libexif' 'libpng' 'libx11' 'imagemagick')
makedepends=('libxt' 'clang')
source=("${url}${pkgname}-${pkgver}.tar.bz2")
sha1sums=('ddbe2ddd1b72209ca131e48b4a70497eeb59dc98')

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
