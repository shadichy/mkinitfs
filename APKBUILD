# Maintainer: Natanael Copa <ncopa@alpinelinux.org>
pkgname=mkinitfs
pkgver=3.7.0
# shellcheck disable=SC2034 # used for git versions, keep around for next time
_ver=${pkgver%_git*}
pkgrel=2
pkgdesc="Tool to generate initramfs images for Android desktop"
url="https://github.com/shadichy/mkinitfs"
arch="all"
license="GPL-2.0-only"
# currently we do not ship any testsuite
options="!check"
makedepends_host="busybox util-linux-dev"
makedepends="$makedepends_host"
depends="
	busybox-binsh
	busybox>=1.28.2-r1
	kmod
	lddtree>=1.25
	mdev-conf
    nlplug-findfs
	"
subpackages="$pkgname-doc"
install="$pkgname.pre-upgrade $pkgname.post-install $pkgname.post-upgrade"
triggers="$pkgname.trigger=/usr/share/kernel/*"

provides="initramfs-generator"
provider_priority=900 # highest

build() {
	make VERSION=$pkgver-r$pkgrel
}

package() {
	make install DESTDIR="$pkgdir"
}
