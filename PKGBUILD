# Contributor: airwoodix <airwoodix@posteo.me>

pkgname=python-sipyco-git
_pkgname=sipyco
pkgver=v1.1.r2.g4e2b999
pkgrel=1
pkgdesc="Simple Python Communications"
arch=('any')
url="https://github.com/m-labs/sipyco"
license=('LGPL3')
provides=('python-sipyco')
depends=('python' 'python-numpy')
source=('git://github.com/m-labs/sipyco.git')
sha256sums=('SKIP')

pkgver() {
    cd $_pkgname
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
    cd $_pkgname
    python setup.py build
}

package() {
    cd $_pkgname
    python setup.py install --root=${pkgdir} --optimize=1
    install -Dm 644 LICENSE ${pkgdir}/usr/share/licenses/python-sipyco
}

