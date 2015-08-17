# Maintainer: Kerrick Staley <mail@kerrickstaley.com>
pkgname=pdf-quench
pkgver=1.0.1
pkgrel=2
pkgdesc='A visual tool for cropping pdf files'
arch=('any')
url='https://code.google.com/p/pdf-quench/'
license=('GPL2')
depends=('pygoocanvas'
         'python2-poppler'
         'python2-pypdf')
source=("https://pdf-quench.googlecode.com/files/${pkgname}_${pkgver}_all.deb")
sha256sums=('caee3c295ab1267a394cffc7909529dfe088be268cdf44897c4baa0747a37624')

package() {
  cd "$pkgdir"
  tar -xzf "$srcdir/data.tar.gz"
  # fix Python stupidity
  sed -ir '1 s/python\b/python2/' "$pkgdir/usr/bin/pdf_quench"
  # fix directory permissions stupidity
  find "$pkgdir/usr" -type d -exec chmod 755 '{}' \;
}
