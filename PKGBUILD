# Maintainer: speps <speps at aur dot archlinux dot org>

pkgname=cecilia5
pkgver=5.0.8
pkgrel=1
pkgdesc="An audio signal processing environment using pyo as its audio engine."
arch=('any')
url="http://code.google.com/p/cecilia5/"
license=('GPL3')
depends=('python2-pyo' 'python2-numpy' 'wxpython')
install="$pkgname.install"
source=("http://cecilia5.googlecode.com/files/Cecilia5_$pkgver-src.tar.bz2"
        "$pkgname.desktop" "$pkgname.sh")
md5sums=('373638ba7168d94ef6bd81bead590e81'
         'e0bcfd6925abdddf6f1dbd2f407afa01'
         'e20b6ed656ed468e6d775415c67518cb')

package() {
  cd "$srcdir/Cecilia5_$pkgver-src"

  # bin
  install -Dm755 ../$pkgname.sh "$pkgdir/usr/bin/$pkgname"

  # data
  install -d "$pkgdir/usr/share/$pkgname"
  cp -a Cecilia5.py Resources "$pkgdir/usr/share/$pkgname"

  # desktop file
  install -Dm 644 ../$pkgname.desktop \
    "$pkgdir/usr/share/applications/$pkgname.desktop"

  # icon
  install -Dm 644 scripts/Cecilia_about_small.png \
    "$pkgdir/usr/share/pixmaps/$pkgname.png"

  # python2 fix
  sed -i "s/python/&2/" `find "$pkgdir" -name "*.py"`
}

# vim:set ts=2 sw=2 et:
