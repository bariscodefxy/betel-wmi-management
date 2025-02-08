# Maintainer: Kediler Birliği

_pkgbase=hp_wmi
pkgname=${_pkgbase}
pkgver=next
pkgrel=1
pkgdesc="HP Victus 16-s1000 wmi driver backported"
url=
license=("GPL")
arch=('x86_64')
depends=('glibc' 'dkms')
makedepends=()
conflicts=("${_pkgbase}")
provides=("${_pkgbase}")
source=('dkms.conf')
sha256sums=('SKIP')

package() {
	install -Dm644 'dkms.conf' "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"

	sed -e "s/@PKGNAME@/${_pkgbase}/g" \
	    -e "s/@PKGVER@/${pkgver}/g" \
	    -i "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"

	cp -dr --no-preserve='ownership' "./${_pkgbase}" "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/src"
}