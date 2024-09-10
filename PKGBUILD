# Maintainer: Knut Ahlers <knut at ahlers dot me>

pkgname=librespeed-cli
pkgver=1.0.11
pkgrel=1
pkgdesc="Command line client for LibreSpeed"
arch=('i686' 'x86_64')
url="https://github.com/librespeed/speedtest-cli"
license=(LGPL3)
makedepends=(git go)
source=("${pkgname}-${pkgver}::git+${url}.git#tag=v${pkgver}")
sha512sums=('bb544d1e6d745fa4bc4d96aecaf05381a680cd70b3ae4737c01bdf1f698e90c55dd7d5937fa975eceab8b0e356370fa47531155ecc431dbdec9e64ead16ac5fe')

build() {
	cd ${srcdir}/${pkgname}-${pkgver}
	bash build.sh
}

package() {
	cd ${srcdir}/${pkgname}-${pkgver}
	install -Dm755 "out/${pkgname}-$(go env GOOS)-$(go env GOARCH)" "${pkgdir}/usr/bin/${pkgname}"
	install -Dm644 "LICENSE" -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
