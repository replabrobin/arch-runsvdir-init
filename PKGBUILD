# Maintainer: replabrobin 
#	hashup of void runit and base runit
#	Archlinux package
# 
# copyright see
# http://creativecommons.org/publicdomain/zero/1.0/

pkgname=arch-runit
pkgver=0.0
pkgrel=1
pkgdesc='Arch native runit package'
url="http://voidlinux.eu"
license=('Creative Commons')
arch=('any')
source=(
	"$pkgname::git+https://github.com/voidlinux/void-runit"i
	)
sha256sums=('SKIP')
# most of depends are not needed, they're present only for clarity
depends=()
makedepends=('git')
optdepends=('sudo: install and update packages as non-root'
			'customizepkg: apply customizepkg modifications')
provides=('arch-runit')
conflicts=(runit systemd libsystemd ignite ignite-git
		runit runit-desktop runit-dietlibc runit-init
		runit-musl runit-run
		runit-run-git
		runit-scripts
		runit-services
		runit-services-git
		void-runit
		)

build() {
	true
	}

pkgver() {
	cd "$pkgname"
	git show -s --format="%ci" HEAD | sed -e 's/-//g' -e 's/ .*//'
	}

package() {
	cd "$srcdir/$pkgname"
	make
	make DESTDIR="$pkgdir/" install
	}
