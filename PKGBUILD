# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>

pkgname=kgrab
pkgver=0.1.1
pkgrel=3
pkgdesc="A fork of KSnapshot. With more funktions as Printing and a standard Menu."
arch=('i686' 'x86_64')
url='http://www.kde-apps.org/content/show.php/KGrab?content=74086'
license=('GPL')
depends=('kdebase-runtime')
makedepends=('pkgconfig' 'cmake' 'automoc4')
options=('docs')
install=${pkgname}.install
source=("http://www.kde-apps.org/CONTENT/content-files/74086-${pkgname}-${pkgver}.tar.bz2")
md5sums=('a014abf9e622832494b8092a8d1da59d')

build() {
  cd $srcdir
  mkdir build
  cd build
  cmake ../${pkgname} \
    -DCMAKE_BUILD_TYPE=Release \
    -DQT_QMAKE_EXECUTABLE=qmake-qt4 \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd ${srcdir}/build
  make DESTDIR=$pkgdir install
}
