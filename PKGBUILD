# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.14.0
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
            '163c4b27e43fc18eb886d520b172784ef1ab2521a5acd2d1cab31591f0daf703'
            '4b0f206b6000ffcc54802c59b9e4f213d57528a996ec76010dbd2a5c4394a4f4')

package () {
  home="${pkgdir}/home/auto-login"
  install -Dm 755 -t "${home}/xsession.d" 50-launch-puppeteer

  install -Dm 755 -t ${pkgdir}/usr/lib/node_modules/puppeteer-kiosk/bin/ puppeteer-kiosk
  install -Dm 644 -t ${pkgdir}/usr/lib/node_modules/puppeteer-kiosk/ opacity.js
  mkdir -p ${pkgdir}/usr/bin
  ln -s /usr/lib/node_modules/puppeteer-kiosk/bin/puppeteer-kiosk ${pkgdir}/usr/bin/

}
