# Maintainer: saber-nyan <saber-nyan@ya.ru>
# Hooks: https://www.reddit.com/r/archlinux/comments/4zrsc3/keep_your_system_fully_functional_after_a_kernel/d6yin0r/
pkgname=kernel-modules-hook
pkgver=0.1.3
pkgrel=1
pkgdesc="Keeps your system fully functional after a kernel upgrade"
arch=('any')
url="https://github.com/saber-nyan/kernel-modules-hook"
license=('unknown')
depends=('rsync')
install="${pkgname}.install"
source=(
		"linux-modules-cleanup.conf"
		"linux-modules-cleanup.service"
		"10-linux-modules-post.hook"
		"10-linux-modules-pre.hook"
		)
sha256sums=(
		"4169b44c297ddb7aad2220c6eba7c7942e3396f92528c59617955ab5560cb4cf"
		"5d947290ef8c94b33c79c531e5615f4c9bea38e7649092d34af3bf0af5b1ca24"
		"94eaaeb612e30992bf0197cb785b3ec1b8e09fc6b2ea437bd59bc4f87f828e76"
		"81cb83bb2a352e4d3ab32bb12bc4f7ad6624e3f6b63dc176d881c73425792633"
		)

package() {
	install -Dm644 'linux-modules-cleanup.conf' "${pkgdir}/usr/lib/tmpfiles.d/linux-modules-cleanup.conf"
	install -Dm644 'linux-modules-cleanup.service' "${pkgdir}/usr/lib/systemd/system/linux-modules-cleanup.service"
	install -Dm644 '10-linux-modules-post.hook' "${pkgdir}/usr/share/libalpm/hooks/10-linux-modules-post.hook"
	install -Dm644 '10-linux-modules-pre.hook' "${pkgdir}/usr/share/libalpm/hooks/10-linux-modules-pre.hook"
}
