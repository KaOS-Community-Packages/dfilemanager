pkgname=dfilemanager-git
_pkgname=dfilemanager
pkgver=r407.73d24ef
pkgrel=2
pkgdesc="Dfilemanager, a QT based crossplatform File browser."
arch=('x86_64')
url="http://dfilemanager.sourceforge.net/"
license=('GPL')
depends=( 'qt5-base' 'solid' 'exiv2' 'poppler')
makedepends=('git' 'cmake' 'qt5-tools' 'qt5-script')
provides=('dfilemanager')
conflicts=('dfilemanager')
source=("${_pkgname}::git://git.code.sf.net/p/dfilemanager/code")
md5sums=('SKIP')
 
pkgver() {
  cd "$_pkgname"
  ( set -o pipefail
    git describe --long | sed -r 's/([^-]*-g)/r\1/;s/-/./g' ||
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  )
}

build() {

    mkdir -p build
    cd build
    
    cmake ../${_pkgname} -DCMAKE_INSTALL_PREFIX=/usr -DQT5BUILD=ON
    make
}
 
package() {
    
    cd build
  
    make DESTDIR=${pkgdir} install
} 

