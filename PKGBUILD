# Maintainer:  Michele Damiano Torelli <me_AT_mdtorelli_DOT_it>
# Contributor: Bartłomiej Piotrowski <barthalion@gmail.com>
# Contributor: Allan McRae <allan@archlinux.org>
# Contributor: Claudio Riva <firetux83@gmail.com>
# Contributor: Stefan Husmann <stefan-husmann@t-online.de>

pkgname=winefish
pkgver=1.3.3
pkgrel=14
pkgdesc="LaTeX editor based on Bluefish with auto-completion and syntax highlighting"
url="http://viettug.github.com/winefish"
arch=('i686' 'x86_64')
license=('GPL')
depends=('gtk2' 'desktop-file-utils')
optdepends=('aspell: for spell check')
install=$pkgname.install
source=("$pkgname-$pkgver.tgz"::"http://sourceforge.net/projects/winefish.berlios/files/$pkgname-$pkgver.tgz/download")
md5sums=('63531e4dde7a53ab3a74e1152c7af1e9')

build() {
  cd ${pkgname}-${pkgver}
  chmod +x configure
  ./configure --prefix=/usr --disable-update-databases \
    --with-freedesktop_org-menu=/usr/share/applications \
    --with-icon-path=/usr/share/pixmaps --mandir=/usr/share/man
  make
}

package() {
  cd ${pkgname}-${pkgver}
  make DESTDIR="${pkgdir}" install
}
