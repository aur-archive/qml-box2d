# Maintainer: Mailson Lira <mailson@gmail.com>

pkgname=qml-box2d
pkgver=20130308
pkgrel=1
pkgdesc="QML bindings to the Box2D physics library"
arch=('i686' 'x86_64')
url="https://gitorious.org/qml-box2d"
license=('LGPL')
depends=('qt4>=4.7')
makedepends=('qt4' 'git')
source=()
md5sums=()

_gitroot="git://gitorious.org/qml-box2d/qml-box2d.git"
_gitname=qml-box2d

build() {
	cd "${srcdir}"
	
	if [ ! -d "${srcdir}/${_gitname}" ]; then
		git clone ${_gitroot}
	else
		cd ${_gitname} && git pull origin
	fi
	
	msg "GIT checkout done."

	cd "${srcdir}"
	cp -rf "${_gitname}" "${_gitname}-build"
	cd "${_gitname}-build"
	
	qmake-qt4
	make
}

package() {
	cd "${srcdir}/${_gitname}-build"
	
	make INSTALL_ROOT="${pkgdir}" install
}
