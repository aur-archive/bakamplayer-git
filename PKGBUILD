# Maintainer: u8sand <u8sand@gmail.com>
pkgname=bakamplayer-git
pkgver=1.9.8
pkgrel=2
pkgdesc="Baka MPlayer is a free and open source, cross-platform, libmpv based multimedia player."
url="https://github.com/u8sand/Baka-MPlayer"
arch=('x86_64' 'i686')
license=('GPLv2')
depends=('mpv' 'qt5-base')
makedepends=('git' 'make')
conflicts=('bakamplayer')
provides=('bakamplayer')
source=("$pkgname"::'git://github.com/u8sand/Baka-MPlayer.git#branch=release')
md5sums=('SKIP')

build() {
  cd "$srcdir/$pkgname"
	./make.sh
	gzip -c etc/doc/bakamplayer.man > etc/doc/bakamplayer.1.gz
}

package() {
  cd "$srcdir/$pkgname"
	install -D "build/Baka-MPlayer" "$pkgdir/usr/bin/bakamplayer"
	install -D "etc/doc/manual.md" "$pkgdir/usr/share/doc/bakamplayer/manual.md"
	install -D "etc/doc/bakamplayer.1.gz" "$pkgdir/usr/share/man/man1/bakamplayer.1.gz"
	install -D "LICENSE" "$pkgdir/usr/share/licenses/bakamplayer/LICENSE"
}
