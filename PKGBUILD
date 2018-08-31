# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=1.3
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
  'Default.ini'
)

sha256sums=('755d1685dcd03f9a596ebd50a462fca223f4bf2eeae20124c6446eab06c1da16'
            '7434ad4651f28a7ca90e71d75e479c38cea309a33300ecfeff037a02659ad994')

package () {
  home="${pkgdir}/home/auto-login"
  config_dir="${home}/.config/compiz/compizconfig"
	install -Dm 644 -t "${config_dir}" 'Default.ini'
  install -Dm 755 -t "${home}/xsession.d" 50-launch-puppeteer
}
