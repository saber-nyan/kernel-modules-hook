# Maintainer: Artoria Pendragon <saber-nyan@ya.ru>
# Hooks: https://www.reddit.com/r/archlinux/comments/4zrsc3/keep_your_system_fully_functional_after_a_kernel/d6yin0r/
pkgname=kernel-modules-hook
pkgver=0.2.0
pkgrel=1
pkgdesc="Keeps your system fully functional after a kernel upgrade"
arch=('any')
url="https://github.com/saber-nyan/kernel-modules-hook"
license=('UNLICENSE')
depends=('rsync')
install="${pkgname}.install"
source=("linux-modules-cleanup.conf"
		"linux-modules-cleanup.service"
		"linux-modules-running-cleanup.service"
		"10-linux-modules-pre.hook"
		"10-linux-modules-post.hook"
		"70-linux-modules-finish.hook"
		"linux-modules-save"
		"linux-modules-restore"
		"UNLICENSE")
sha256sums=('4169b44c297ddb7aad2220c6eba7c7942e3396f92528c59617955ab5560cb4cf'
            '5d947290ef8c94b33c79c531e5615f4c9bea38e7649092d34af3bf0af5b1ca24'
            '028014ba194d4b69529a7f40b55e92be2815b8b589e97e7eb7cb9c2da39a148d'
            '896bd84e35cf90647aee2d9cdb7e4324e67ca84df21f9df5fb57a982d6093bab'
            '7fd8e77e6dab4f7c99788ff500b2d5b19fae7a23ef6789f0651e2659baac2818'
            'fa9edd33ae5461652901a20109b15998461dad8d2b9b7ff507101ade1360df32'
            '7cd1e1c53c90374a53c4a2159cf51c4905251ba288149dcd24c842b387820fd8'
            '3773fd228d9806808669575bd3cfe06636d2f16504c2d2ab2bb1c3bdae645a55'
            '7e12e5df4bae12cb21581ba157ced20e1986a0508dd10d0e8a4ab9a4cf94e85c')

package() {
	install -Dm644 'linux-modules-cleanup.conf' "${pkgdir}/usr/lib/tmpfiles.d/linux-modules-cleanup.conf"
	install -Dm644 'linux-modules-cleanup.service' "${pkgdir}/usr/lib/systemd/system/linux-modules-cleanup.service"
	install -Dm644 'linux-modules-running-cleanup.service' "${pkgdir}/usr/lib/systemd/system/linux-modules-running-cleanup.service"
	install -d "${pkgdir}/usr/lib/systemd/system/basic.target.wants"
	ln -s ../linux-modules-running-cleanup.service "${pkgdir}/usr/lib/systemd/system/basic.target.wants/linux-modules-running-cleanup.service"
	install -Dm644 '10-linux-modules-pre.hook' "${pkgdir}/usr/share/libalpm/hooks/10-linux-modules-pre.hook"
	install -Dm644 '10-linux-modules-post.hook' "${pkgdir}/usr/share/libalpm/hooks/10-linux-modules-post.hook"
	install -Dm644 '70-linux-modules-finish.hook' "${pkgdir}/usr/share/libalpm/hooks/70-linux-modules-finish.hook"
	install -Dm755 'linux-modules-save' "${pkgdir}/usr/share/libalpm/scripts/linux-modules-save"
	install -Dm755 'linux-modules-restore' "${pkgdir}/usr/share/libalpm/scripts/linux-modules-restore"
	install -Dm644 'UNLICENSE' "${pkgdir}/usr/share/licenses/${pkgname}/UNLICENSE"
}
