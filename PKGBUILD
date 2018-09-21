# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.10
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

sha256sums=('a727e7061fde6b4a2501327a9e5a0d06a3e9948c355bb5eb9aa2dcfd0babad89'
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
