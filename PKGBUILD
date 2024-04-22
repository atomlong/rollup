# Maintainer: Bernardo Kuri <aur+rollup@bkuri.com>
# Contributor: Luis Martinez <luis dot martinez at disroot dot org>
# Contributor: Simon Legner <Simon.Legner@gmail.com>

pkgname=rollup
pkgver=4.16.1
pkgrel=1

arch=('any')
depends=('nodejs')
license=('MIT')
makedepends=('npm')
noextract=("${pkgname}-${pkgver}.tgz")
options=('!emptydirs')
pkgdesc="Next-generation ES6 module bundler"
sha256sums=('413479ae6d0fa4b10b960adbe480347a292131f2d6022877f1582486d5ee744c')
source=("${pkgname}-${pkgver}.tgz::https://registry.npmjs.org/${pkgname}/-/${pkgname}-${pkgver}.tgz")
url="https://rollupjs.org/"

package() {
	export NODE_ENV='production'
	npm install -g \
		--cache "${srcdir}/npm-cache" \
		--prefix "${pkgdir}/usr" \
		"${pkgname}-${pkgver}.tgz"

	chown -R root:root "${pkgdir}/"

	install -dv "${pkgdir}/usr/share/licenses/${pkgname}/" "${pkgdir}/usr/share/doc/${pkgname}/"
	ln -sv "/usr/lib/node_modules/${pkgname}/LICENSE.md" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	ln -sv "/usr/lib/node_modules/${pkgname}/README.md" -t "${pkgdir}/usr/share/doc/${pkgname}/"
}
