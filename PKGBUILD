# Maintainer: Emil Lundberg <emil@emlun.se> (emlun)

pkgname='systemlund'
pkgver='1.0.0'
pkgrel=1
pkgdesc="emlun's systemd units"
license=('custom:unlicense')
arch=('any')
url='https://github.com/emlun/systemlund'
optdepends=(
  'slock: For screenlock@.service'
  'openvpn: For restart-openvpn-client@.service'
)
source=('git+https://github.com/emlun/systemlund.git')
sha1sums=('SKIP')

package() {
  install -d -m 755 "${pkgdir}/usr/lib/systemd/system"
  install -D -m 444 "${srcdir}/${pkgname}"/*.service "${srcdir}/${pkgname}"/*.target "${pkgdir}/usr/lib/systemd/system"
  install -D -m 444 "${srcdir}/${pkgname}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
