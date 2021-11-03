pkgname=nqptp-git
pkgver=r172.f7f731b
pkgrel=1
arch=("x86_64")
source=(
  "git+https://github.com/mikebrady/nqptp.git#branch=development"
)
sha1sums=("SKIP")

pkgver() {
  cd "$srcdir/nqptp"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  cd "$srcdir/nqptp"
  autoreconf -fi
}

build() {
  cd "$srcdir/nqptp"
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/nqptp"
  make DESTDIR="$pkgdir/" install
}
