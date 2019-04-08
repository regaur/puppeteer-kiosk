# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.17.0
pkgrel=1
pkgdesc="Launch puppeteer in auto-login session"
arch=('x86_64')
license=('GPL')
groups=()

depends=(
  'puppeteer'
  'lightdm-autologin>=2.7'
  'compiz-user-service'
)

conflicts=(
  'launch-compiz'
  'fadein-windows'
)

source=(
  'puppeteer-kiosk'
  'opacity.js'
  'puppeteer-kiosk@.service'
)

sha256sums=('52a7789699471fd7c5aa191981b983170c633da3e6430f4b4b4935736af42b77'
            '4b0f206b6000ffcc54802c59b9e4f213d57528a996ec76010dbd2a5c4394a4f4'
            '5340f61722566c12284c604d0cd159d7d85ce76b46176fed378df0f457f29145')

package () {
  home="${pkgdir}/home/auto-login"
  install -Dm 755 -t ${pkgdir}/usr/lib/node_modules/puppeteer-kiosk/bin/ puppeteer-kiosk
  install -Dm 644 -t ${pkgdir}/usr/lib/node_modules/puppeteer-kiosk/ opacity.js
  mkdir -p ${pkgdir}/usr/bin
  ln -s /usr/lib/node_modules/puppeteer-kiosk/bin/puppeteer-kiosk ${pkgdir}/usr/bin/

  install -Dm 644 -t "${pkgdir}/usr/lib/systemd/user" 'puppeteer-kiosk@.service'
}
