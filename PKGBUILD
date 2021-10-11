# Maintainer: Emil Lundberg <emil@emlun.se> (emlun)

pkgname='systemlund'
pkgver='2.1.0'
pkgrel=1
pkgdesc="emlun's systemd units"
license=('custom:unlicense')
arch=('any')
url='https://github.com/emlun/systemlund'
optdepends=(
  'slock: For screenlock@.service'
  'swaylock: For screenlock-sway@.service'
  'openvpn: For restart-openvpn-client@.service'
)
source=('git+https://github.com/emlun/systemlund.git')
sha1sums=('SKIP')

package() {
  install -d -m 755 "${pkgdir}/usr/lib/systemd/system" "${pkgdir}/etc/systemd/system"
  install -D -m 444 "${srcdir}/${pkgname}"/*.service "${srcdir}/${pkgname}"/*.target "${pkgdir}/usr/lib/systemd/system"
  install -D -m 444 "${srcdir}/${pkgname}"/etc/*.service "${srcdir}/${pkgname}"/*.target "${pkgdir}/etc/systemd/system"

  for dir in "${srcdir}/${pkgname}"/*.service.d ; do
    local _confdir=${dir#${srcdir}/${pkgname}/}
    install -d -m 755 "${pkgdir}/usr/lib/systemd/system/${_confdir}"
    install -D -m 444 "${dir}"/*.conf "${pkgdir}/usr/lib/systemd/system/${_confdir}/"
  done

  install -D -m 444 "${srcdir}/${pkgname}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
