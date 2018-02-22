pkgname=dfilemanager
pkgver=0.1.20180222
_commit=73d24ef5f0a726ae480cc54d3644b8ef71607bdc
pkgrel=1
pkgdesc="A QT based crossplatform File browser"
arch=('x86_64')
url="http://dfilemanager.sourceforge.net/"
license=('GPL')
depends=('qt5-x11extras' 'qt5-base' 'solid' 'exiv2' 'poppler')
makedepends=('cmake' 'qt5-script' 'qt5-tools')
provides=('dfilemanager-git')
conflicts=('dfilemanager-git')
replaces=('dfilemanager-git')
source=("https://sourceforge.net/code-snapshots/git/d/df/dfilemanager/code.git/dfilemanager-code-$_commit.zip")
md5sums=('08b6b6da52f9a25d95a54040cad606c1')

build() {

	mkdir -p build
	cd build

	cmake ../${filemanager-code-$_commit} -DCMAKE_INSTALL_PREFIX=/usr -DQT5BUILD=ON
	make
}

package() {

	cd build
	
	make DESTDIR=${pkgdir} install
}

