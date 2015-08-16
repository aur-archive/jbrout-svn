# Maintainer : Ennoia <ennoia at laposte.net>
# Previous Maintainer : Jonathan Schaeffer <joschaeffer at gmail.com>

_svnrev=366
pkgname=jbrout-svn
pkgver=0.3.${_svnrev}
pkgrel=2
pkgdesc="A photo manager with support for IPTC keywords"
arch=('i686' 'x86_64')
url="http://code.google.com/p/jbrout/"
license=('GPL2')
depends=('python2' 'python2-lxml' 'pygtk' 'python2-imaging' 'fbida' 'jhead' 'python2-exiv2>=0.1.2' 'perl-image-exiftool')
makedepends=('subversion')
#optdepends=('psyco2-svn')
provides=('jbrout')
conflicts=('jbrout')

_svnsource=http://jbrout.googlecode.com/svn/trunk/

build() {
	svn export --revision ${_svnrev} $_svnsource/dist/data $srcdir/jbrout
	svn export --revision ${_svnrev} $_svnsource/jbrout $pkgdir/usr/lib/jbrout
	sed -i 's/python/python2/1' $srcdir/jbrout/jbrout
	install -D -m755 $srcdir/jbrout/jbrout $pkgdir/usr/bin/jbrout
	install -D -m644 $srcdir/jbrout/jbrout.desktop	$pkgdir/usr/share/applications/jbrout.desktop
}
