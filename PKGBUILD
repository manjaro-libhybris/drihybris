# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=drihybris
pkgver=0.2.0
pkgrel=1
pkgdesc='DRIHYBRIS extension (based on DRI3) for buffer sharing on libhybris-based adaptations'
url='https://github.com/gemian/drihybris'
arch=(i686 x86_64 armv7h aarch64)
license=()
conflicts=(drihybris)
provides=(drihybris)
depends=(xorg-server xorgproto android-headers)
makedepends=(xorg-server-devel git)
source=('git+https://github.com/gemian/drihybris.git#commit=d275fa5d57cb6a659da0a76a2d9a9e3eeee56b1a')
sha256sums=('SKIP')

prepare() {
  cd ${pkgname}
  NOCONFIGURE=1 ./autogen.sh
}

build() {
  cd ${pkgname}
  export CPLUS_INCLUDE_PATH=/usr/iclude/android:/usr/include/android/hybris
  export C_INCLUDE_PATH=/usr/iclude/android:/usr/include/android/hybris
  ./configure --prefix=/usr
  make
}

package() {
  cd ${pkgname}
  make DESTDIR="${pkgdir}" install
}
