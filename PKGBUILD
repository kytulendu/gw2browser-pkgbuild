# Maintainer: Khralkatorrix <garuda2550@gmail.com>

pkgname=gw2browser
_pkgname=gw2browser
pkgver=1.0.r921.8f06f75a
pkgrel=1
pkgdesc="Opens a Guild Wars 2 .dat file and allows the user to browse and extract its
files."
arch=('x86_64')
url="https://github.com/kytulendu/gw2browser"
license=('GPL3')
depends=('libgw2dattools' 'libgw2formats' 'glm' 'glew' 'openal' 'libogg' 'libvorbis' 'mpg123' 'libwebp' 'wxwidgets-gtk3')
makedepends=('cmake' 'libgw2dattools' 'libgw2formats' 'glm' 'glew' 'openal' 'libogg' 'libvorbis' 'mpg123' 'libwebp' 'wxwidgets-gtk3' 'wxwidgets-common')
source=("git+https://github.com/kytulendu/gw2browser.git")
sha256sums=('SKIP')

prepare() {
    mkdir -p build
}

pkgver() {
    cd "${srcdir}/$_pkgname"
    echo "1.0.r$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

build() {
    cd "${srcdir}/$_pkgname"
    cmake . -DCMAKE_INSTALL_PREFIX="/usr"
    make
}

package() {
    cd "${srcdir}/$_pkgname"
    make DESTDIR="$pkgdir" install
}
