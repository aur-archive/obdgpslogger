# Maintainer: Gary Briggs <chunky@icculus.org>

pkgname=obdgpslogger
pkgver=0.16
pkgrel=1
pkgdesc='Log OBDII data and GPS in your car while driving. OBDII Simulator included.'
arch=('i686' 'x86_64' 'armv5tel' 'arm' 'armv5')
url='http://icculus.org/obdgpslogger/'
license=('GPL2')
source=("$url/downloads/$pkgname-$pkgver.tar.gz")
md5sums=('771b9bba11426825ede1e98071a02eaf')
depends=('gpsd' 'bluez')
makedepends=('cmake' 'subversion')

build() {
	cd "$srcdir/$pkgname-$pkgver"

	mkdir build; cd build

	cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX='/usr' -DOBD_DISABLE_GUI=ON .. || return 1

	make || return 1

	make DESTDIR="$pkgdir/" install || return 1
}

