#Maintainer: foalsrock <foalsrock at gmail dot com>

pkgname=gnome-shell-extension-battery-remaining-time
pkgver=20120305
pkgrel=1
pkgdesc="Gnome Shell extension to show remaining time for battery near the icon on the top panel."
arch=('any')
url="https://extensions.gnome.org/extension/230/battery-remaining-time/"
license=('GPL2')
depends=('gnome-shell')
makedepends=('git')
groups=('gnome-shell-extensions')

_gitroot="git://github.com/dadexix86/battery-remaining-time.git"
_gitname="battery-remaining-time"

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi

  msg "GIT checkout done or server timeout"
}

package() {
    install -Dm 644 "${srcdir}/battery-remaining-time/extension.js" "${pkgdir}/usr/share/gnome-shell/extensions/battery-remaining-time@dadexix86.github.com/extension.js"
    install -Dm 644 "${srcdir}/battery-remaining-time/metadata.json" "${pkgdir}/usr/share/gnome-shell/extensions/battery-remaining-time@dadexix86.github.com/metadata.json"
    install -Dm 644 "${srcdir}/battery-remaining-time/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
