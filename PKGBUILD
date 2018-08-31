# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.4
pkgrel=1
pkgdesc="Launch compiz and puppeteer in auto-login session"
arch=('x86_64')
license=('GPL')
groups=()

depends=(
  'puppeteer'
  'lightdm-autologin'
  'compiz-core'
)

conflicts=(
  'launch-compiz'
  'fadein-windows'
)

source=(
  '50-launch-puppeteer'
)

sha256sums=('09c9712d788117f66217234eb81863cd034b8f1ddb825d88b3a88774abd62ae7')

package () {
  home="${pkgdir}/home/auto-login"
  install -Dm 755 -t "${home}/xsession.d" 50-launch-puppeteer
}
