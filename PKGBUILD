# Maintainer: faerbit <faerbit at gmail dot com>

_pkgname=lxqt-lightdm-greeter
pkgname=$_pkgname-git
pkgver=56.561ba62
pkgrel=1
pkgdesc="A greeter for lightdm"
arch=('i686' 'x86_64')
url="http://www.lxde.org"
license=('LGPL')
depends=('liblxqt' 'liblightdm-qt4')
makedepends=('git' 'cmake' 'lxqt-powermanagement')
provides=($_pkgname)
conflicts=($_pkgname)
source=("git://github.com/lxde/$_pkgname.git"
        "lxqt-lightdm-greeter.install")
md5sums=('SKIP'
         '66f002eb73b5709c2c13582153ee1557')
sha1sums=('SKIP'
          'cbc5f1ce7e62964fa38b04951bdc3770330dcc68')
sha256sums=('SKIP'
            '56ddc9977bb4c65987154b3f4711b9aab3e331dac4c0b1a4e00c8fd0cd174ccf')
sha384sums=('SKIP'
            'd1ba69007dc7e36457ba99321f0791726707aa1cfbc2d2809cabe7785ef19854765eab7eecdc0a71c5e22888c303e147')
sha512sums=('SKIP'
            '4adbd499801bec9af1cc815688e8a40a7ba54bd20b0a868ee8f0510711332ce3c4eb2e3b0dc5786ae1501934a3f157859a65619669d0c485d32792023c8f633a')
install=lxqt-lightdm-greeter.install
_gitname=$_pkgname

pkgver() {
    cd "$srcdir/$_gitname"
    echo "$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

build() {
    cd "$srcdir/$_gitname"
    mkdir -p build
    cd build
    cmake -DCMAKE_INSTALL_PREFIX=/usr  ..
    make
}

package() {
    cd "$srcdir/$_gitname"
    cd build
    make DESTDIR="$pkgdir" install
}
