# Maintainer: Bernardo Kuri <aur+rollup@bkuri.com>
# Contributor: Luis Martinez <luis dot martinez at disroot dot org>
# Contributor: Simon Legner <Simon.Legner@gmail.com>

pkgname=rollup
pkgver=4.7.0
4.9.0
pkgrel=1
pkgdesc="Next-generation ES6 module bundler"
arch=('any')
url="https://rollupjs.org/"
license=('MIT')
depends=('nodejs')
makedepends=('npm')
changelog=CHANGELOG.md
options=('!emptydirs')
source=("$pkgname-$pkgver.tgz::https://registry.npmjs.org/$pkgname/-/$pkgname-$pkgver.tgz")
noextract=("$pkgname-$pkgver.tgz")
sha256sums=('7782b9cdd6724c6f1f966098a5e1c3fee4ee4912366d5a29dbd3bae64df9fe4a')
PURGE_TARGETS=('CHANGELOG.md')

package() {
	export NODE_ENV=production
	npm install -g \
		--cache "$srcdir/npm-cache" \
		--prefix "$pkgdir/usr" \
		"$pkgname-$pkgver.tgz"
	chown -R root:root "$pkgdir/"

	install -dv "$pkgdir/usr/share/licenses/$pkgname/" "$pkgdir/usr/share/doc/$pkgname/"
	ln -sv "/usr/lib/node_modules/$pkgname/LICENSE.md" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
	ln -sv "/usr/lib/node_modules/$pkgname/README.md" -t "$pkgdir/usr/share/doc/$pkgname/"
}
