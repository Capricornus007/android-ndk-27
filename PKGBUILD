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
sha1sums=('852f88a00ac895b54701cb2fef54fede2e41beea'
          '22105e410cf29afcf163760cc95522b9fb981121')
sha256sums=('54291dd9ed0f28dcb39a84c7c6d8dea4617bf0588fb1ce0e5c176435f9767a5a'
            '601246087a682d1944e1e16dd85bc6e49560fe8b6d61255be2829178c8ed15d9')

package() {
  install -Ddm755 "$pkgdir/opt/android-sdk/ndk"
  mv "android-ndk-r27d" "$pkgdir/opt/android-sdk/ndk/$pkgver"

  install -Dm644 android-ndk-27.sh -t "$pkgdir/etc/profile.d/"

  install -Dm644 "$pkgdir/opt/android-sdk/ndk/$pkgver/NOTICE" \
    "$pkgdir/usr/share/licenses/$pkgname/NOTICE"
}
