# Contributor: Ermak <ermak@email.it>
pkgname=fpdns
pkgver=0.9.3
pkgrel=1
pkgdesc="Program that remotely determines DNS server versions"
url="http://code.google.com/p/fpdns/"
depends=('')
license=('BSD')
options=('!emptydirs')
arch=('i686' 'x86_64')
source=('http://fpdns.googlecode.com/files/Net-DNS-Fingerprint-0.9.3.tar.gz') 
md5sums=('16f1fbc9e5c8b935a0a48a509dc58899')

build() {
  cd  ${srcdir}/Net-DNS-Fingerprint-0.9.3
  eval `perl -V:archname`
  /usr/bin/perl Makefile.PL \
      INSTALLARCHLIB=/usr/lib/perl5/current/${archname} \
      INSTALLSITELIB=/usr/lib/perl5/site_perl/current \
      INSTALLSITEARCH=/usr/lib/perl5/site_perl/current/${archname}
  /usr/bin/make || return 1
  /usr/bin/make DESTDIR=${pkgdir} install
  /usr/bin/find ${pkgdir} -name '.packlist' -delete
  /usr/bin/find ${pkgdir} -name '*.pod' -delete
}

