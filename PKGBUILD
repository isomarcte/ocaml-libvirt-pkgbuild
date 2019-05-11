# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: David Strawn <isomarcte a__t gmail d__o__t c__o__m>
_pkgname_base='ocaml-libvirt'
pkgname="${_pkgname_base}-git"
pkgver='20180921'
pkgrel=1
epoch=
pkgdesc='OCaml bindings for libvirt'
url='https://people.redhat.com/rjones/virt-top/'
arch=('x86_64')
license=('GPL2')
depends=('ocaml' 'libvirt')
makedepends=('ocaml-findlib' 'autoconf' 'git' 'coreutils')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=('!strip')
install=
changelog=
source=("git://git.annexia.org/${_pkgname_base}.git#commit=fe02985a0d620bd9ac6363608b5e757030ffc5e4")
noextract=()
md5sums=('SKIP')
sha1sums=('SKIP')
sha224sums=('SKIP')
sha256sums=('SKIP')
sha384sums=('SKIP')
sha512sums=('SKIP')
validpgpkeys=()

build() {
    cd "${_pkgname_base}"
    autoreconf
    ./configure --prefix /usr
    make all
    make opt
}

package() {
    local -r OCAMLFIND_DESTDIR="${pkgdir}/usr/lib/ocaml/${_pkgname_base}"
    install -d "$OCAMLFIND_DESTDIR"
    cd "${_pkgname_base}"
    env DESTDIR="${pkgdir}" OCAMLFIND_DESTDIR="$OCAMLFIND_DESTDIR" make install-opt
}
