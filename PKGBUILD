# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.2
pkgrel=1
pkgdesc="Launch puppeteer in auto-login session"
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
  '50-launch-puppeteer'
)
sha256sums=('877011744a267161a1a461ab4c7d93e3e64551fb8c6abb79340c25bde35db740')

package () {
  install -Dm 755 -t "${pkgdir}/home/auto-login/xsession.d" 50-launch-puppeteer
}
