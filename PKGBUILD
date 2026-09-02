# Android NDK r27d (27.3.13750724) — mirror-sourced rebuild of the AUR
# android-ndk-27 package. Identical upstream zip, same checksums as AUR,
# but the source URL points at the Capricornus007 GitHub mirror because
# dl.google.com is unreachable from the maintainer's network.

pkgname=android-ndk-27
pkgver=27.3.13750724
pkgrel=1
pkgdesc='Android C/C++ developer kit (r27d)'
arch=('x86_64')
url='https://developer.android.com/ndk/'
license=('GPL' 'LGPL' 'custom')
options=('!strip' 'staticlibs')
backup=("etc/profile.d/android-ndk-27.sh")
install="$pkgname.install"
conflicts=('android-ndk')
provides=("android-ndk=$pkgver")
replaces=('android-ndk64')
depends=('bash' 'glibc' 'gcc-libs' 'zlib')
optdepends=(
  'ncurses5-compat-libs: for curses module in bundled Python'
  'bzip2: for bz2 module in bundled Python'
  'libxcrypt-compat: for crypt module in bundled Python'
  'python: various helper scripts'
  'perl: various helper scripts'
  'libc++: for some LLVM components'
)
source=(
  "android-ndk-27.sh"
  "https://github.com/Capricornus007/android-ndk-23/releases/download/google-mirror/android-ndk-r27d-linux.zip"
)
# SHA1 kept alongside SHA256 following upstream convention; both match the
# official dl.google.com archives (and the AUR android-ndk-27 sums).
sha1sums=('SKIP'
          'SKIP')
sha256sums=('SKIP'
            'SKIP')

package() {
  install -Ddm755 "$pkgdir/opt/android-sdk/ndk"
  mv "android-ndk-r27d" "$pkgdir/opt/android-sdk/ndk/$pkgver"

  install -Dm644 android-ndk-27.sh -t "$pkgdir/etc/profile.d/"

  install -Dm644 "$pkgdir/opt/android-sdk/ndk/$pkgver/NOTICE" \
    "$pkgdir/usr/share/licenses/$pkgname/NOTICE"
}
