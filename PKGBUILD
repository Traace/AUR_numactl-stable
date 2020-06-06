# Maintainer:   Serede Sixty Six          <serede dot dev at gmail dot com>
# Maintainer:   Jose Fernando Zazo Rollon <josefernando dot zazo at naudit dot es>

_pkgname=numactl
pkgname=${_pkgname}-stable
pkgver=2.0.13
pkgrel=1
pkgdesc='Simple NUMA policy support with support for i686, x86_64, aarm64 and others'
arch=('any')
license=('GPLv2')
depends=('glibc')
makedepends=('gcc')
provides=('numactl')
conflicts=('numactl')
url="https://github.com/numactl/numactl"
source=("https://github.com/numactl/numactl/releases/download/v${pkgver}/${_pkgname}-${pkgver}.tar.gz")
sha256sums=('991e254b867eb5951a44d2ae0bf1996a8ef0209e026911ef6c3ef4caf6f58c9a')

build() {
  cd "${srcdir}/${_pkgname}-${pkgver}"
  ./configure --prefix="${pkgdir}/usr"
  make -j$(nproc)
}

package() {
  cd "${srcdir}/${_pkgname}-${pkgver}"
  make install
  rm -rfv "${pkgdir}/usr/share/man/man2/move_pages.2"
}

# vim:set ft=sh ts=2 sw=2 et:
