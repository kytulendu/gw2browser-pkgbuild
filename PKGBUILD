# Maintainer: Khralkatorrix <garuda2550@gmail.com>

pkgname=gw2browser
_pkgname=gw2browser
pkgver=1.0.r887.f3ac07d9
pkgrel=1
pkgdesc="Opens a Guild Wars 2 .dat file and allows the user to browse and extract its
files."
arch=('x86_64')
url="https://github.com/kytulendu/gw2browser"
license=('GPL3')
depends=('libgw2dattools' 'libgw2formats' 'glm' 'glew' 'openal' 'libogg' 'libvorbis' 'mpg123' 'libwebp')
makedepends=('cmake' 'libgw2dattools' 'libgw2formats' 'glm' 'glew' 'openal' 'libogg' 'libvorbis' 'mpg123' 'libwebp')
source=("git://github.com/kytulendu/gw2browser.git")
sha256sums=('SKIP')

prepare() {
    mkdir -p build
}

pkgver() {
    cd $_pkgname
    echo "1.0.r$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

build() {
    cd $_pkgname
    cmake . -DCMAKE_INSTALL_PREFIX="/usr"
    make
}

package() {
    cd $_pkgname
    make DESTDIR="$pkgdir" install
}
