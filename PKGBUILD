pkgname=lib32-brother-dcpj715w-cups
pkgver=1.1.3
pkgrel=1
license=('custom:Brother Industries')
pkgdesc="LPR: 1.1.3-1  cupswrapper: 1.1.3-1"
url="http://solutions.brother.com/linux/en_us/index.html"

arch=('x86_64')
depends=('a2ps' 'cups' 'lib32-glibc')
#makedepends=('rpmextract')


install=brother-dcpj715w.install
source=("http://www.brother.com/pub/bsc/linux/dlf/dcpj715wcupswrapper-1.1.3-1.i386.rpm" \
        "http://www.brother.com/pub/bsc/linux/dlf/dcpj715wlpr-1.1.3-1.i386.rpm" \
        fix_lp.patch)
md5sums=('116b6abd6f347752873ce4597830120e'
         '8e41b6ad92b96e9003237e4f3e7362b3'
         'c40cdcdc7643ac67171a2f191a8924bd')

build() {
  cd "$startdir"
	patch -Np0 < fix_lp.patch
}

package() {
	install -d $pkgdir/usr/bin
	install -d $pkgdir/var/spool/lpd
  install -Dm755 "$srcdir"/usr/bin/brprintconf_dcpj715w "$pkgdir"/usr/bin/
	cp -R $srcdir/opt $pkgdir/
}
