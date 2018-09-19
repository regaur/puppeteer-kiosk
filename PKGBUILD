# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.8
pkgrel=1
pkgdesc="Launch compiz and puppeteer in auto-login session"
arch=('x86_64')
license=('GPL')
groups=()

depends=(
  'puppeteer'
  'lightdm-autologin>=2.7'
  'compiz-core'
  'background'
)

conflicts=(
  'launch-compiz'
  'fadein-windows'
)

source=(
  '50-launch-puppeteer'
  'puppeteer-kiosk'
  'opacity.js'
)

sha256sums=('e8d914cff533672bfd6603444d74aa901c8d6e3d6d6b3f2559d86210a34fae08'
            'dbcfe3f2bb752de179caaf7a62f29400416939b9e86d2079f3757ee48c8b5b04'
            '0e748649b9856b88a7b874ba08d62bff59ce75bb37393d4c895a845ee815fdb0')

package () {
  home="${pkgdir}/home/auto-login"
  install -Dm 755 -t "${home}/xsession.d" 50-launch-puppeteer

  install -Dm 755 -t ${pkgdir}/usr/lib/node_modules/puppeteer-kiosk/bin/ puppeteer-kiosk
  install -Dm 644 -t ${pkgdir}/usr/lib/node_modules/puppeteer-kiosk/ opacity.js
  mkdir -p ${pkgdir}/usr/bin
  ln -s /usr/lib/node_modules/puppeteer-kiosk/bin/puppeteer-kiosk ${pkgdir}/usr/bin/

}
