pkgname=numlockx
pkgver=1.2
pkgrel=1
pkgdesc='Turns on the numlock key in X11.'
arch=('x86_64')
url='http://home.kde.org/~seli/numlockx/'
license=('MIT')
depends=('libxtst')
#source=(http://home.kde.org/~seli/${pkgname}/${pkgname}-${pkgver}.tar.gz)
source=(http://pkgs.fedoraproject.org/repo/pkgs/${pkgname}/${pkgname}-${pkgver}.tar.gz/be9109370447eae23f6f3f8527bb1a67/${pkgname}-${pkgver}.tar.gz)
sha512sums=('efaaa67e8b2723cb1e8461dde664f1f8e9b21f34edfe2e1135a6b756fa2843aed1a386f2f9d70bd62ddae9aedfeeff856a18da8b542f2cff440f93b38e5a853e')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  
  ./configure --prefix=/usr x_includes=/usr/include/X11 x_libraries=/usr/lib
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  
  make prefix="${pkgdir}/usr" install
  
  # Install the custom MIT license
  install -Dm0644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
