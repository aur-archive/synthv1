# Maintainer: speps <speps at aur dot archlinux dot org>

pkgname=synthv1
pkgver=0.3.6
pkgrel=1
pkgdesc="An old-school all-digital 4-oscillator subtractive polyphonic synthesizer with stereo fx"
arch=(i686 x86_64)
url="http://$pkgname.sourceforge.net/$pkgname-index.html"
license=('GPL')
groups=('lv2-plugins')
depends=('jack' 'liblo' 'lv2' 'qt5-base' 'shared-mime-info' 'hicolor-icon-theme')
install="$pkgname.install"
source=("http://download.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz")
md5sums=('f25832fc0f3e269f6e251e914da06451')

prepare() {
  cd $pkgname-$pkgver

  # x86_64 lib path fix
  sed -i "s/lib64/lib/" src/src_lv2{,ui}.pro
}

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
