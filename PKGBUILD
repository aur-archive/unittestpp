# Maintainer: Jorge Araya Navarro <elcorreo@deshackra.com>
# Contributor: Piotr Beling <qwak@w8.pl>
# Contributor: Vianney le Clément <vleclement AT gmail · com>
pkgname=unittestpp
pkgver=1.4
pkgrel=5
pkgdesc="A lightweight unit testing framework for C++"
arch=('i686' 'x86_64')
url="http://unittest-cpp.sourceforge.net/"
depends=('gcc-libs')
source=("http://downloads.sourceforge.net/project/unittest-cpp/UnitTest%2B%2B/$pkgver/unittest-cpp-$pkgver.zip"
        'unittest++.pc')
md5sums=('bd373a53403ed51ea1bbb60b1952d7e3'
         'fa35c8a0274264dcb75e5106c5b3deb7')
license=('MIT')
options=('staticlibs')

build() {
  cd "$srcdir/UnitTest++"
  make all
}

package() {
  install -dm755 "$pkgdir/usr/lib/pkgconfig"
  install -m644 unittest++.pc "$pkgdir/usr/lib/pkgconfig"

  cd "$srcdir/UnitTest++"
  
  install -dm755 "$pkgdir/usr/include/unittest++/Posix"
  install -m644 src/*.h "$pkgdir/usr/include/unittest++"
  install -m644 src/Posix/*.h "$pkgdir/usr/include/unittest++/Posix"
  
  install -dm755 "$pkgdir/usr/lib"
  install -m644 libUnitTest++.a "$pkgdir/usr/lib"
  ln -s libUnitTest++.a "$pkgdir/usr/lib/libunittest++.a"
  
  install -dm755 "$pkgdir/usr/share/licenses/unittest++"
  install -m644 COPYING "$pkgdir/usr/share/licenses/unittest++/LICENSE"
  install -dm755 "$pkgdir/usr/share/doc/unittest++"
  install -m644 README "$pkgdir/usr/share/doc/unittest++/README"
  install -m644 docs/UnitTest++.html "$pkgdir/usr/share/doc/unittest++/UnitTest++.html"
}

# vim:set ts=2 sw=2 et:
