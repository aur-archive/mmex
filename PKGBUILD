# Maintainer: Jaroslav Lichtblau <dragonlord@aur.archlinux.org>
# Contributor: TDY <tdy@gmx.com>

pkgname=mmex
pkgver=0.9.9.0
pkgrel=2
pkgdesc="An easy-to-use personal finance suite (Money Manager Ex)"
arch=('i686 x86_64')
url="http://www.codelathe.com/mmex/"
license=('GPL')
depends=('wxgtk2.8')
makedepends=('boost' 'gettext')
optdepends=('cups: for printing support')
source=(http://www.codelathe.com/mmex/installer/linux/${pkgname}_${pkgver}_src.tar.bz2)
md5sums=('f6d284fb58c77aed4f3c425778d31680')

build() {
  cd "${srcdir}"/${pkgname}_${pkgver}

  ./configure LIBS="-lpthread -lm -ldl" \
          --prefix=/usr \
	  --enable-unicode \
	  --enable-shared \
	  --with-wxshared \
	  --with-gtk \
	  --with-wx-config=/usr/lib/wx/config/gtk2-unicode-release-2.8
  #LIBS="-ldl -lm -lpthread"
  make
}

package() {
  cd "${srcdir}"/${pkgname}_${pkgver}
  make DESTDIR="${pkgdir}" install
}
