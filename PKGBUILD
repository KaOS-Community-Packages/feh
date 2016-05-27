pkgname=feh
pkgver=2.15.4
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
sha1sums=('f271fc3b7b6a75dc30661c5f64c0f8ea0300a1ce')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr exif=1 help=1 stat64=1
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
