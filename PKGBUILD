# Maintainer: Thomas Dziedzic < gostrc at gmail >

pkgname=libuser
pkgver=0.57.1
pkgrel=2
pkgdesc='A standardized interface for manipulating and administering user and group accounts.'
arch=('i686' 'x86_64')
license=('LGPL')
url='https://fedorahosted.org/libuser/'
depends=('python2')
source=("https://fedorahosted.org/releases/l/i/libuser/libuser-${pkgver}.tar.xz")
md5sums=('be82c6941264d0b4bd04f95fb342ec7d')

build() {
  cd ${pkgname}-${pkgver}

  export PYTHON=python2

  ./configure \
    --prefix=/usr \
    --disable-gtk-doc-html \
    --disable-rpath

  sed -i 's/SUBDIRS = po docs/SUBDIRS = po/' Makefile

  make
}

package() {
  cd ${pkgname}-${pkgver}

  make DESTDIR=${pkgdir} install
}
