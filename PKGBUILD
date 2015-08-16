# Maintainer: Joel Teichroeb <joel@teichroeb.net>

pkgname=gw2formats-git
pkgver=r38.56429c1
pkgrel=1
pkgdesc="Type-safe library for reading the data in Guild Wars 2's files."
arch=(i686 x86_64)
url="https://github.com/klusark/gw2formats"
license=('GPL3')
makedepends=('git' 'cmake')
source=(git://github.com/klusark/gw2formats.git)
sha1sums=('SKIP')

pkgver() {
	cd gw2formats
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd gw2formats
	mkdir build
	cd build
	cmake -DCMAKE_INSTALL_PREFIX=/usr ..
	make
}

package() {
	cd gw2formats
	cd build
	make DESTDIR=${pkgdir} install

}
