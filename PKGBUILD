# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=2.1.0
pkgrel=2
pkgdesc="Launch puppeteer in auto-login session"
arch=('x86_64')
license=('GPL')
groups=()

depends=(
  'puppeteer'
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

sha256sums=('323fa1ce59eb05c35dd6ef0a63a6e0ca99c32f5cf66a3758eb378bb27518a27d')

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
