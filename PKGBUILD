# Maintainer: dasonk < dasonk at gmail dot com >
# Contributor: Meow < meow at linux dot cn >

pkgname=rstudio-desktop-preview-bin
pkgver=0.98.879
pkgrel=1
pkgdesc="A new integrated development environment (IDE) for R (The preview binary from the website)."
arch=('x86_64') # May work for i686 but hasn't been tested
license=('GPL')
url="http://www.rstudio.com/ide/download/preview"
depends=('r>=2.11.1' 'qtwebkit' 'shared-mime-info')
conflicts=('rstudio-desktop' 'rstudio-desktop-git' 'rstudio-desktop-bin')
provides=("rstudio-desktop=${pkgver}")
options=(!strip)
#_x86md5=e017b55b9ece034880d52f2f2e4d92c1
_x64md5=6ae26ac250bf35e71e53ab4370e0a988		
case "$CARCH" in
#	'i686')
		#_arch=i386
		#md5sums=($_x86md5)
		#;;
	'x86_64')
		_arch=amd64
		md5sums=($_x64md5)
		;;
esac    
source=("https://s3.amazonaws.com/rstudio-dailybuilds/rstudio-${pkgver}-${_arch}.deb")

install="$pkgname".install

package() {
  msg "Converting debian package..."
  cd "$srcdir"
  tar zxpf data.tar.gz -C "$pkgdir"
  install -dm755 "$pkgdir/usr/bin"
  cd "$pkgdir/usr/lib/rstudio/bin"
  rm lib*.so.*
  cd "$pkgdir/usr/bin"
  ln -s -f ../lib/rstudio/bin/rstudio rstudio-bin
}
