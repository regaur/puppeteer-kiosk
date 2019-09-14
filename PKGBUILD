# Maintainer: Jan Boelsche <jan@lagomorph.de>
pkgname=puppeteer-kiosk
pkgver=2.14.0
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

sha256sums=('cbc330e3aad875a367bebc94378f3582ac33aec9368ff7b46b63a2a925c7faf0')

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
