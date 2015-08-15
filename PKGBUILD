# Maintainer: Antonio Rojas <nqn1976 @ gmail.com>

pkgname=digikam-devel
_appname=digikam
pkgver=4.4.0
pkgrel=1
pkgdesc="Digital photo management application for KDE - Unstable version"
arch=("i686" "x86_64")
url="http://www.digikam.org"
license=('GPL')
depends=('kdepimlibs' 'libbaloo4' 'opencv' 'liblqr' 'qjson' 'kdeedu-marble' 'libkipi' 'libkexiv2' 'libkdcraw' 'libksane')
makedepends=('automoc4' 'cmake' 'boost' 'doxygen' 'hugin' 'libgpod' 'eigen' 'imagemagick' 'qt-gstreamer')
optdepends=("libgpod: support for Apple iPod audio devices"
	"hugin: for the Panorama tool" "imagemagick: Video slideshow plugin" "qt-gstreamer: Video slideshow plugin")
conflicts=('digikam' 'kipi-plugins' 'libkface' 'libkgeomap' 'libkvkontakte' 'libmediawiki')
provides=('digikam' 'kipi-plugins' 'libkface' 'libkgeomap' 'libkvkontakte' 'libmediawiki')
install="$pkgname.install"
#source=("http://download.kde.org/unstable/$_appname/$_appname-${pkgver/_/-}.tar.bz2")
source=("http://download.kde.org/stable/$_appname/$_appname-$pkgver.tar.bz2")
md5sums=('ffafd3d4fe7e920830fe7a7452852542')

build() {
  cd $_appname-${pkgver/_/-}
  mkdir build
  cd build
  cmake .. -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package(){
  cd $_appname-${pkgver/_/-}/build
  make DESTDIR=$pkgdir install

  rm "${pkgdir}"/usr/share/locale/kde4/*/LC_MESSAGES/libkipi.mo
}
