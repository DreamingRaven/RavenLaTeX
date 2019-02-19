# Maintainer: George Raven <GeorgeRavenCommunity AT outlook dot com>
# Non-standard variables
_vcs="git" # allows script to be reusable by abstracting out vcs
_fragment='branch='"master" # as above
_pkgsrcname="sharelatex" # sets downloaded folder name and pkgname to be the same

pkgname=${_pkgsrcname}-${_vcs}
pkgver=r273.808da2a
pkgrel=1
pkgdesc="an open-source online real-time collaborative LaTeX editor"
arch=('x86_64')
url="https://github.com/sharelatex/sharelatex"
license=('AGPL3') # GNU Afferno General Public License
groups=()
depends=()
makedepends=(${_vcs}) # 'bzr', 'git', 'mercurial' or 'subversion'
provides=("${_pkgsrcname}")
conflicts=()
replaces=()
backup=()
options=()
install=
source=(${_pkgsrcname}'::'${_vcs}'+'${url}'#'${_fragment})
noextract=()
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${_pkgsrcname}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
	# printf "%s" "$(git describe --long | sed 's/\([^-]*-\)g/r\1/;s/-/./g')"
}

prepare() {
	cd "$srcdir/${_pkgsrcname}"
	git checkout ${branch} # get off of makepkg branch
	# patch -p1 -i "$srcdir/${pkgname}.patch"
}

build() {
	cd "$srcdir/${_pkgsrcname}"
	# ./autogen.sh
	# ./configure --prefix=/usr
	# make
}

check() {
	cd "$srcdir/${_pkgsrcname}"
	# make -k check
}

package() {
	cd "$srcdir/${_pkgsrcname}"
	# make DESTDIR="$pkgdir/" install
}
