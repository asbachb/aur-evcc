# Maintainer: Benjamin Asbach <svetlemodry@archlinux.org>

pkgname=evcc
pkgver=0.120.3
pkgrel=1
pkgdesc="evcc optimises sustainability when charging electric vehicles. It enables charging using as much self-generated power as possible."
arch=('x86_64' 'aarch64')
url="https://evcc.io/"
license=('MIT')
makedepends=('go' 'npm')
source=(${pkgname}-${pkgver}.tar.gz::https://github.com/evcc-io/${pkgname}/archive/${pkgver}.tar.gz)
sha512sums=('4b796984ed573ec3e3f08a20e86fcfe532f2ad1258fee1b2482f0ade03ad0e9c45b74fac8a9641d18ebe50c53a7c9585e0f83b9b67611770862c061863d82796')

build() {
  cd "${srcdir}"/${pkgname}-${pkgver}
  make install-ui
  make ui
  make install
  make
}

package() {
  cd "${srcdir}"/${pkgname}-${pkgver}
  install -Dm755 "${pkgname}" "${pkgdir}"/usr/bin/${pkgname}
}
