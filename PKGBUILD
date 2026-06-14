

pkgname=badapple-py
pkgver=1.0.0
pkgrel=1
pkgdesc="ASCII Bad Apple player for Linux terminals written in Python"
arch=('any')
url="https://github.com/Raj-1727/badapple-py"
license=('MIT')

depends=(
    'python'
    'python-pillow'
    'ffmpeg'
    'figlet'
    'lolcat'
)

makedepends=('curl')

source=(
    "$pkgname-$pkgver.tar.gz::$url/archive/refs/tags/v$pkgver.tar.gz"
)

sha256sums=('SKIP')

_VIDEO_URL="https://github.com/trung-kieen/bad-apple-ascii/raw/refs/heads/main/bad_apple.mp4"

build() {
    mkdir -p "$srcdir/_build"

    curl -L \
        "$_VIDEO_URL" \
        -o "$srcdir/_build/bad_apple.mp4"
}

package() {
    cd "$srcdir/$pkgname-$pkgver"

    install -Dm755 badapple-py \
        "$pkgdir/usr/bin/badapple-py"

    install -Dm644 \
        "$srcdir/_build/bad_apple.mp4" \
        "$pkgdir/usr/share/badapple-py/badapple.mp4"

    install -Dm644 LICENSE \
        "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

    install -Dm644 README.md \
        "$pkgdir/usr/share/doc/$pkgname/README.md"
}
