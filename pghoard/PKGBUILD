# Maintainer: Sampson Crowley <sampsonsprojects@gmail.com>

pkgname=pghoard
pkgver=1.4.0
pkgrel=1
pkgdesc="Automated PostgreSQL backups and replication with cloud solutions"
arch=()
url="https://github.com/ohmu/pghoard"
arch=(i686 x86_64)
license=(APACHE)
depends=(python python-psycopg2 python-requests snappy python-dateutil python-cryptography python-boto python-google-api-python-client python-systemd)
options=()
replaces=()
backup=()
source=(
  $pkgname.$pkgver.tar.xz
)

build() {
  cd $srcdir/$pkgname
  make
}

package() {
cd $srcdir/$pkgname
python setup.py install --root="$pkgdir/" --prefix="/usr" --optimize=1
install -D $pkgname.unit $pkgdir/usr/lib/systemd/system/$pkgname.service
mkdir -p $pkgdir/var/lib/pghoard
cp -R ./* $pkgdir/var/lib/pghoard/
# easy_install dist/pghoard-$pkgver.dev93-py3.6.egg
}

md5sums=('2b6e26456c256729d59ac408abc66618')
