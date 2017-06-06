# Maintainer: Hiroaki Mikami <hiroaki8270+github@gmail.com>
pkgname=update-git-repository
pkgver=r3.cf5c103
pkgrel=1
pkgdesc=""
arch=("x86_64")
url=""
license=('MIT')
groups=()
depends=()
makedepends=('systemd', 'grive')
provides=("${pkgname}")
conflicts=("${pkgname}")
replaces=()
backup=()
options=()
source=()
install=
noextract=()
md5sums=()

pkgver() {
  cd "$srcdir"

  # Git, no tags available
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  # Add systemd service
  cd "$startdir"
  mkdir -p "$pkgdir/etc/systemd/user"
  cp ./grive-sync.service "$pkgdir/etc/systemd/user/"
  cp ./grive-sync.timer "$pkgdir/etc/systemd/user/"
}
