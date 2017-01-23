pkgname=feh
pkgver=2.18.1
pkgrel=1
pkgdesc='Fast and light imlib2-based image viewer'
url='http://feh.finalrewind.org/'
license=('custom:MIT')
arch=('x86_64')
depends=('giblib' 'curl' 'libxinerama' 'libexif')
optdepends=('perl: feh-cam, webcam wrapper for feh'
            'imagemagick: support more file formats')
makedepends=('libxt')
source=("${url}${pkgname}-${pkgver}.tar.bz2")
sha1sums=('d2db9a81fb6b675df198ad13c6cf00b6b3dec63f')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr exif=1 help=1 stat64=1
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install

	install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	# Repair permissions
	chmod 644 "${pkgdir}/usr/share/icons/hicolor/"{48x48/apps/feh.png,scalable/apps/feh.svg}
}
