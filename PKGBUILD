# Maintainer: David Parrish <daveparrish@gmail.com>

pkgname=bitsquare
pkgver=0.2.1
pkgrel=1
pkgdesc="Bitsquare is a cross-platform desktop application that allows users to trade national currency (dollars, euros, etc) for bitcoin without relying on centralized exchanges"
arch=('x86_64')
url="https://bitsquare.io/"
license=('AGPL3')
provides=('bitsquare')
source_x86_64=("https://github.com/bitsquare/bitsquare/releases/download/v0.2.1/bitsquare-0.2.1.deb")
sha256sums_x86_64=("103913e6ec4d42a26069646c892a87bb14b9e88afd6bbe8a2d18ba99bff18c45")
_binname=Bitsquare

prepare() {
  tar -Jxvf data.tar.xz
}

package() {
  install -d "$pkgdir"/{opt/,usr/bin/,usr/share/applications,/usr/share/pixmaps,/usr/share/licenses/$pkgname}

  # Install all .deb files into /opt.
  cp -r "$srcdir/opt" "$pkgdir"

  # Symlink some files to complete install.
  ln -s "/opt/$_binname/$_binname" "$pkgdir/usr/bin/$pkgname"
  ln -s "/opt/$_binname/${_binname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
  ln -s "/opt/$_binname/${_binname}.png" "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
}
