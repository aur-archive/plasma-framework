# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=plasma-framework
pkgver=4.99.0
pkgrel=1
pkgdesc='Plasma library and runtime components based upon KF5 and Qt5'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/playground/libs/plasma-framework'
license=('LGPL')
depends=('qt5-quickcontrols' 'kidletime' 'kitemmodels' 'threadweaver'
         'kwallet' 'kdeclarative' 'kunitconversion'
         'kross' 'kdnssd' 'kdelibs4support' 'kinit'
         'kactivities-frameworks' 'qt5-quick1')
makedepends=('extra-cmake-modules' 'qt5-tools')
optdepends=('kde-workspace: provide a Plasma shell')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('bb8077f5858643939bc002428cfcc338')

prepare() {
  mkdir -p build
}

build() {
  export CMAKE_PREFIX_PATH="/opt/kf5"

  cd build
  cmake ../plasma-framework-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
