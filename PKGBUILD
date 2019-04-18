# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=2.5.0
pkgrel=1
pkgdesc="Launch puppeteer in auto-login session"
arch=('x86_64')
license=('GPL')
groups=()

depends=(
  'puppeteer'
  'imagemagick'
  'lightdm-autologin>=2.7'
  'compiz-user-service'
  'xdotool'
)
makedepends=('npm')

conflicts=(
  'launch-compiz'
  'fadein-windows'
)

source=(
  'puppeteer-kiosk@.service'
)

sha256sums=('f0c11da12b0e3b00c0bd51d4b8e2c11d440f7f28be66680bc572c6a01f75cdeb')

pkgver () {
  npm view ${pkgname}@latest version
}

package () {
  source "$HOME/.nvm/nvm.sh"
  nvm use 10.8.0
  local _npmdir="${pkgdir}/usr/lib/node_modules/"
  mkdir -p $_npmdir
  npm install -g --prefix "${pkgdir}/usr" ${pkgname}@${pkgver}

  install -Dm 644 -t "${pkgdir}/usr/lib/systemd/user" 'puppeteer-kiosk@.service'
}
