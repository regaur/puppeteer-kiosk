# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.1
pkgrel=1
pkgdesc="Auto-start puppeteer"
arch=('x86_64')
license=('GPL')
groups=()

depends=(
  'puppeteer'
  'lightdm-autologin'
)

makedepends=('')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()

source=(
  '.xsession'
)
sha256sums=('877011744a267161a1a461ab4c7d93e3e64551fb8c6abb79340c25bde35db740')

package () {
  install -Dm 755 -t "${pkgdir}/home/auto-login/" .xsession
}
