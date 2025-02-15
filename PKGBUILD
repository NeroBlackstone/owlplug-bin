# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=owlplug-bin
pkgver=1.28.1
pkgrel=1
pkgdesc="Audio plugin manager. Small tool to manage VST / AU / LV2 plugins on Windows, MacOS and Linux."
arch=('x86_64')
url="https://owlplug.com/"
license=('GPL-3.0')
source=("https://github.com/DropSnorz/OwlPlug/releases/download/${pkgver}/OwlPlug-${pkgver}.deb")
sha256sums=('aab63b6831c5d0c87e0d94cddd13cf866e024eedb10bfb3179f87e834efaadb2')

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
    
    install -dm644 "$pkgdir/usr/share/applications"
    cp opt/owlplug/lib/owlplug-OwlPlug.desktop "$pkgdir/usr/share/applications/"
}
