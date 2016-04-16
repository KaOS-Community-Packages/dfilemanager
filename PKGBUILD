pkgname=dfilemanager
pkgver=0.1.20160416
_commit=73d24ef5f0a726ae480cc54d3644b8ef71607bdc
pkgrel=1
pkgdesc="A QT based crossplatform File browser"
arch=('x86_64')
url="http://dfilemanager.sourceforge.net/"
license=('GPL')
depends=('qt5-x11extras' 'qt5-base' 'qt5-script' 'qt5-tools')
optdepends=('solid')
makedepends=('cmake')
source=("https://sourceforge.net/code-snapshots/git/d/df/dfilemanager/code.git/dfilemanager-code-$_commit.zip")
md5sums=('08b6b6da52f9a25d95a54040cad606c1')

build() {
    cd $srcdir/dfilemanager-code-$_commit/dfm
    cmake ../ -DCMAKE_INSTALL_PREFIX=/usr -DQT5BUILD=ON
    make
}

package() {
    cd $srcdir/dfilemanager-code-$_commit/dfm
    make DESTDIR="$pkgdir/" install
}

