# Maintainer: Simon Legner <Simon.Legner@gmail.com>
pkgname=rollup
pkgver=2.58.0
pkgrel=1
pkgdesc="Next-generation ES6 module bundler"
arch=(any)
url="https://rollupjs.org/"
license=('MIT')
depends=('nodejs')
makedepends=('npm')
optdepends=()
source=(https://registry.npmjs.org/$pkgname/-/$pkgname-$pkgver.tgz)
noextract=($pkgname-$pkgver.tgz)

package() {
  cd $srcdir
  local _npmdir="$pkgdir/usr/lib/node_modules/"
  mkdir -p $_npmdir
  cd $_npmdir
  npm install -g --prefix "$pkgdir/usr" $pkgname@$pkgver
  find "${pkgdir}"/usr -name package.json -exec sed -i '/"_where"/d' '{}' '+'
  find "${pkgdir}"/usr -type d -exec chmod 755 {} +
}

sha256sums=('8377f0d2563e4660302b99435758328a363d9c4d9103398595cd720ca47f3dca')
