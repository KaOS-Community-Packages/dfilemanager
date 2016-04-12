pkgname=dfilemanager
pkgver=0.1.20160412
_commit=6cd4f58b1940dd7e7baf65a1bb9a5dac487ff4c5
pkgrel=1
pkgdesc="A QT based crossplatform File browser"
arch=('x86_64')
url="http://dfilemanager.sourceforge.net/"
license=('GPL')
depends=('qt5-x11extras' 'qt5-base' 'qt5-script' 'qt5-tools')
optdepends=('solid')
makedepends=('cmake')
source=("https://sourceforge.net/code-snapshots/git/d/df/dfilemanager/code.git/dfilemanager-code-$_commit.zip")
md5sums=('5bec8b9c1353369db3f712be549ef51e')

build() {
    cd $srcdir/dfilemanager-code-$_commit/dfm
    cmake ../ -DCMAKE_INSTALL_PREFIX=/usr -DQT5BUILD=ON
    make
}

package() {
    cd $srcdir/dfilemanager-code-$_commit/dfm
    make DESTDIR="$pkgdir/" install
}
