# Maintainer: Doug Newgard <scimmia22 at hotmail dot com>
# Contributor: twa022 <twa022 at gmail dot com>

pkgname=enki-svn
_pkgname=enki
pkgver=84380
pkgrel=1
pkgdesc="Photo album manager based on EFL"
arch=('i686' 'x86_64')
url="http://www.enlightenment.org"
license=('LGPL2.1')
depends=('enlil-svn' 'elementary')
makedepends=('subversion')
options=('!libtool')
source=("svn+http://svn.enlightenment.org/svn/e/trunk/$_pkgname")
md5sums=('SKIP')

pkgver() {
  cd "$SRCDEST/$_pkgname"

  LC_ALL=C svn info | awk '/Last Changed Rev/ {print $4}'
}

build() {
  cd "$srcdir/$_pkgname"

  ./autogen.sh --prefix=/usr

  make
}

package() {
  cd "$srcdir/$_pkgname"
  
  make DESTDIR="$pkgdir" install
}
