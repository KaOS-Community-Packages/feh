pkgname=feh
pkgver=2.17
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
sha1sums=('e8a85382a9829ddf9680835c91f330a89c9b8fdd')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr exif=1 help=1 stat64=1
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install

	install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
