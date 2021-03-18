# Maintainer: Artoria Pendragon <saber-nyan@ya.ru>
# Hooks: https://www.reddit.com/r/archlinux/comments/4zrsc3/keep_your_system_fully_functional_after_a_kernel/d6yin0r/
pkgname=kernel-modules-hook
pkgver=0.1.8
pkgrel=1
pkgdesc="Keeps your system fully functional after a kernel upgrade"
arch=('any')
url="https://github.com/saber-nyan/kernel-modules-hook"
license=('UNLICENSE')
install="${pkgname}.install"
source=("linux-modules-cleanup.conf"
		"linux-modules-cleanup.service"
		"10-linux-modules-post.hook"
		"10-linux-modules-pre.hook"
		"UNLICENSE")
sha256sums=('4169b44c297ddb7aad2220c6eba7c7942e3396f92528c59617955ab5560cb4cf'
            '5d947290ef8c94b33c79c531e5615f4c9bea38e7649092d34af3bf0af5b1ca24'
            '3b90321be042ea728e27bef530aeb22cecc4cd0aeda625ab4a72fb46dae3abee'
            'dc99191391b847deecf81abded84b03eb832ca1b36e56a4a4deec8bf1332f051'
            '7e12e5df4bae12cb21581ba157ced20e1986a0508dd10d0e8a4ab9a4cf94e85c')

package() {
	install -Dm644 'linux-modules-cleanup.conf' "${pkgdir}/usr/lib/tmpfiles.d/linux-modules-cleanup.conf"
	install -Dm644 'linux-modules-cleanup.service' "${pkgdir}/usr/lib/systemd/system/linux-modules-cleanup.service"
	install -Dm644 '10-linux-modules-post.hook' "${pkgdir}/usr/share/libalpm/hooks/10-linux-modules-post.hook"
	install -Dm644 '10-linux-modules-pre.hook' "${pkgdir}/usr/share/libalpm/hooks/10-linux-modules-pre.hook"
	install -Dm644 'UNLICENSE' "${pkgdir}/usr/share/licenses/${pkgname}/UNLICENSE"
}
