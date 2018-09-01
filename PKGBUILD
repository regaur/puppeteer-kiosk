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
  'lightdm-autologin>=2.7'
  'compiz-core'
)

conflicts=(
  'launch-compiz'
  'fadein-windows'
)

source=(
  '50-launch-puppeteer'
)


package () {
  home="${pkgdir}/home/auto-login"
  install -Dm 755 -t "${home}/xsession.d" 50-launch-puppeteer
}
