
pkgname=shell-advancedutils
pkgver=2.0.0
pkgrel=1
pkgdesc="Advanced commands to extend SH/Bash shell scripting into a more powerful language"
# arch package url is https://github.com/kata198/shell-advancedutils-pkg
url="https://github.com/kata198/shell-advancedutils"
arch=(i686 x86_64)
license=(apache)
depends=(python bash)
builddepends=(fakeroot)
source=("https://github.com/kata198/shell-advancedutils/archive/${pkgver}.tar.gz")
md5sums=('776bd1189c89ec9fb93febda6c740a4f')

build() {
  cd "${pkgname}-${pkgver}"

  make

}

package() {
  mkdir -p "${pkgdir}"

  cd "${srcdir}/${pkgname}-${pkgver}"

  make install DESTDIR="$pkgdir"

  echo "Changing owner of ${pkgdir}"
  chown -R root:root "${pkgdir}"
  if [ $? -ne 0 ];
  then
    echo "Failed chown..."
  fi
  stat "${pkgdir}"
}
