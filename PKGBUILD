# Maintainer: saber-nyan <saber-nyan@ya.ru>
# Hooks: https://www.reddit.com/r/archlinux/comments/4zrsc3/keep_your_system_fully_functional_after_a_kernel/d6yin0r/
pkgname=kernel-modules-hook
pkgver=0.1.1
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
		"linux-modules-post.hook"
		"linux-modules-pre.hook"
		)
sha256sums=(
		"4169b44c297ddb7aad2220c6eba7c7942e3396f92528c59617955ab5560cb4cf"
		"5d947290ef8c94b33c79c531e5615f4c9bea38e7649092d34af3bf0af5b1ca24"
		"39a124a4fb5cf3f2cace0bd5bd203a6d5d78aac1eb7dfb7610b91839281ac58b"
		"86cedb612d06f618beb0b47a06d78fe1a34e726ceb213dfa6ba498415c1e53b4"
		)

package() {
	cd "$pkgname-$pkgver"
	install -Dm644 'linux-modules-cleanup.conf' "${pkgdir}/usr/lib/tmpfiles.d/linux-modules-cleanup.conf"
	install -Dm644 'linux-modules-cleanup.service' "${pkgdir}/usr/lib/systemd/system/linux-modules-cleanup.service"
	install -Dm644 'linux-modules-post.hook' "${pkgdir}/usr/share/libalpm/hooks/linux-modules-post.hook"
	install -Dm644 'linux-modules-pre.hook' "${pkgdir}/usr/share/libalpm/hooks/linux-modules-pre.hook"
}
