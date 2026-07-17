# Maintainer: fft
# Contributor: Lukas Rose <public@lrose.de>

pkgname=geany-plugin-jsonprettifier
pkgver=1.7.0
pkgrel=1
pkgdesc="Clean up unformatted JSON in Geany editor"
arch=('i686' 'x86_64')
url="https://plugins.geany.org/jsonprettifier.html"
license=('GPL-2.0-or-later')
depends=('geany' 'yajl')
source=("https://github.com/zhgzhg/Geany-JSON-Prettifier/archive/refs/tags/v${pkgver}.tar.gz")
b2sums=('2f72f06d8411072c5b77a9404f6e53fa5ec3b9a3702c5b74280a8c1a61d64aad6e6ac1b8e994264a2fdf1d98253a94b2a5c47d1c7323916ad6a5266f1dd02f70')

build() {
  cd "Geany-JSON-Prettifier-${pkgver}"
  # NB: upstream uses own yajl version. Here yajl library from archlinux repo is used instead.
  gcc -DLOCALEDIR=\"\" -DGETTEXT_PACKAGE=\"zhgzhg\" geany_json_prettifier.c -fPIC -shared $(pkg-config --cflags geany) -lgeany -lyajl -o jsonprettifier.so
}

package() {
  mkdir -p "${pkgdir}/usr/lib/geany"
  cp "Geany-JSON-Prettifier-${pkgver}/jsonprettifier.so" "${pkgdir}/usr/lib/geany"
}
