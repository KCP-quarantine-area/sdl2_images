pkgname=sdl2_image
pkgver=2.0.1
pkgrel=1
pkgdesc="A simple library to load images of various formats as SDL surfaces (Version 2)"
arch=('x86_64')
url="http://www.libsdl.org/projects/SDL_image"
license=('MIT')
depends=('sdl2' 'libpng' 'libtiff' 'libjpeg-turbo' 'libwebp')
makedepends=('cmake')
source=("https://www.libsdl.org/projects/SDL_image/release/SDL2_image-${pkgver}.tar.gz")
sha512sums=('99ed5f7b69966cea5fcf9173e7270167c24b55ab459774f10dbf90f26dcb9d5f118971ffd4e583a83148976f44ca166474669398a561169d24ffba80f852306f')

build() {
  cd "${srcdir}/SDL2_image-${pkgver}/"
  ./configure --disable-static --prefix=/usr
  make
}

package() {
  cd "${srcdir}/SDL2_image-${pkgver}/"

  make DESTDIR="${pkgdir}/" install
  install -Dm644 COPYING.txt "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
