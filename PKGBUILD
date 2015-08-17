# Maintainer: Hilton Medeiros <medeiros.hilton@gmail.com>

pkgname=python2-bjoern-git
_gitname=bjoern
pkgver=343.00e1400
pkgrel=1
pkgdesc="A screamingly fast Python WSGI server written in C."
arch=('i686' 'x86_64' 'armv5h' 'armv6h' 'armv7h')
url="https://github.com/jonashaag/bjoern"
license=('BSD')
depends=('libev' 'python2')
makedepends=('git' 'python2-distribute')
conflicts=('python2-bjoern')
provides=('python2-bjoern')
source=('git://github.com/jonashaag/bjoern.git')
md5sums=('SKIP')

pkgver() {
  cd $_gitname
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd $_gitname
  git submodule sync
  git submodule update --init
}

package() {
  cd $_gitname
  python2 setup.py install --prefix=/usr --root="$pkgdir" -O1
  install -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
} 
