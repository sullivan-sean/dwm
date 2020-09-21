# Maintainer: Sean Sullivan <sean@seansullivan.ai>
pkgname=dwm
pkgver=6.2
pkgrel=1
epoch=1
pkgdesc="Sean's dynamic window manager with sensible defaults, etc."
arch=('i686' 'x86_64')
url="https://github.com/sullivan-sean/dwm"
license=('MIT')
options=(zipman)
depends=('libx11' 'libxinerama' 'libxft' 'freetype2')
source=('git://github.com/sullivan-sean/dwm'
				'config.h')
sha1sums=('SKIP' 'SKIP')

build() {
  cd "$srcdir/${pkgname}"
	cp "$srcdir/config.h" config.h
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  local installopts='--mode 0644 -D'
  cd "$srcdir/${pkgname}"
	make PREFIX=/usr DESTDIR="$pkgdir/" install
  install $installopts LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install $installopts README "${pkgdir}/usr/share/doc/${pkgname}/README"
	install $installopts "$srcdir/dwm.desktop" "${pkgdir}/usr/share/xsessions/dwm.desktop"
}

