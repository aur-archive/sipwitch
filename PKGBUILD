# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: David Sugar <dyfet@gnutelephony.org>
pkgname=sipwitch
pkgver=1.9.0
pkgrel=1
#epoch=
pkgdesc="A federated call server for the SIP protocol"
arch=('x86_64' 'i686')
url="http://www.gnutelephony.org"
license=('GPL3')
groups=()
depends=('ucommon>=6.0.0' 'avahi' 'libexosip2')
makedepends=()
options=()
install=sipwitch.install
changelog=
source=(ftp://ftp.gnu.org/gnu/sipwitch/$pkgname-$pkgver.tar.gz)
noextract=()
md5sums=('9813083c7cbd473cab740672185b41f2')

build() {
	cd "$srcdir/$pkgname-$pkgver"
	./configure --prefix=/usr --with-initrddir=none
	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
	install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
