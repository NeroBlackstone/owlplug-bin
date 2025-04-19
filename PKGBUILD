# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=owlplug-bin
pkgver=1.29.0
pkgrel=1
pkgdesc="Audio plugin manager. Small tool to manage VST / AU / LV2 plugins on Windows, MacOS and Linux."
arch=('x86_64')
url="https://owlplug.com/"
license=('GPL-3.0')
source=("https://github.com/DropSnorz/OwlPlug/releases/download/${pkgver}/OwlPlug-${pkgver}.deb")
sha256sums=('3d8efa8bb1714d8111ac3ee7bad3664991084d257fced219e279fbd5e0c51b9e')

prepare() {
    mkdir -p "$srcdir/$pkgname-$pkgver"
    cd "$srcdir/$pkgname-$pkgver"
    ar x "$srcdir/OwlPlug-${pkgver}.deb"
    tar --use-compress-program=unzstd -xvf data.tar.zst
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    
    install -dm755 "$pkgdir/opt"
    cp -r opt/* "$pkgdir/opt/"
    
    install -dm755 "$pkgdir/usr/share/applications"
    cp opt/owlplug/lib/owlplug-OwlPlug.desktop "$pkgdir/usr/share/applications/"
}
