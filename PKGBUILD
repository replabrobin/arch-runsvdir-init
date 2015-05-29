# Maintainer: replabrobin 
#	hashup of void runit and base runit
#	Archlinux package
# 
# copyright see
# http://creativecommons.org/publicdomain/zero/1.0/

pkgname=arch-runit
pkgver=2.1.2
pkgrel=1
pkgdesc='Arch native runit package'
url='http://smarden.org/runit/'
license=('Creative Commons')
arch=('any')
source=("http://smarden.org/runit/runit-2.1.2.tar.gz"
		"void-runit::git+https://github.com/voidlinux/void-runit"
		)
sha256sums=('6fd0160cb0cf1207de4e66754b6d39750cff14bb0aa66ab49490992c0c47ba18'
			'SKIP')
# most of depends are not needed, they're present only for clarity
depends=()
makedepends=('git')
optdepends=('sudo: install and update packages as non-root'
			'customizepkg: apply customizepkg modifications')
provides=('arch-runit')
conflicts=(
		runit systemd libsystemd ignite ignite-git
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
