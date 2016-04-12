pkgname=dfilemanager
pkgver=0.r406.6cd4f58
pkgrel=1
pkgdesc="A QT based crossplatform File browser"
arch=('x86_64')
url="http://dfilemanager.sourceforge.net/"
license=('GPL')
depends=( 'qt5-x11extras' 'qt5-base' 'qt5-script' 'qt5-tools')
makedepends=('cmake')
source=("${pkgname}::git://git.code.sf.net/p/dfilemanager/code")
md5sums=('SKIP')

pkgver() {
  cd $pkgname
  printf "0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd $srcdir/$pkgname/dfm
    cmake ../ -DCMAKE_INSTALL_PREFIX=/usr -DQT5BUILD=ON
    make
}

package() {
    cd $srcdir/$pkgname/dfm
    make DESTDIR="$pkgdir/" install
}
