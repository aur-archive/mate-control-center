# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni "Talorno" Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>
# Contributor: hekel <hekel@archlinux.info>

pkgname=mate-control-center
pkgver=1.6.2
pkgrel=1
pkgdesc="The Control Center for MATE"
url="http://mate-desktop.org"
arch=('i686' 'x86_64')
license=('GPL')
depends=('dbus-glib' 'dconf' 'desktop-file-utils' 'gsettings-desktop-schemas'
         'gtk2' 'mate-desktop' 'mate-file-manager' 'mate-icon-theme' 'mate-menus'
         'mate-settings-daemon' 'mate-window-manager' 'libgtop' 'libmatekbd'
         'libunique' 'librsvg' 'libxss' 'libxt' 'startup-notification')
makedepends=('docbook2x' 'mate-common' 'mate-doc-utils' 'perl-xml-parser')
options=('!emptydirs')
groups=('mate')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('d3aa9434dde63bd176e995cbb8408fd673f6eed5')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --sysconfdir=/etc \
        --sbindir=/usr/bin \
        --localstatedir=/var \
        --disable-static \
        --disable-scrollkeeper \
        --disable-update-mimedb
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
    rm -f "${pkgdir}/usr/share/applications/mimeinfo.cache"
}
