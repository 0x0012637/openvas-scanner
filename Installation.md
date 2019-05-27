# Manual for install and start openvas 

#
#
#
If you like learn in detail about this arsenal just visit https://www.greenbone.net/


#
#Let's install the pre-requisites.
#
    wget http://security-cdn.debian.org/debian-security/pool/updates/main/g/gcc-4.9/gcc-4.9-base_4.9.2-10+deb8u2_amd64.deb && wget http://security-cdn.debian.org/debian-security/pool/updates/main/g/gcc-4.9/libasan1_4.9.2-10+deb8u2_amd64.deb && dpkg -i gcc-4.9-base_4.9.2-10+deb8u2_amd64.deb && dpkg -i libasan1_4.9.2-10+deb8u2_amd64.deb && sudo apt-get install dash git-core autoconf libtool gettext autopoint automake autogen nettle-dev gcc pkg-config libssh-gcrypt-dev libgnutls28-dev libglib2.0-dev libpcap-dev libgpgme-dev bison libksba-dev libsnmp-dev libgcrypt20-dev libp11-kit-dev libtspi-dev libunistring-dev valgrind libasan1 libubsan0 nodejs softhsm2 datefudge lcov libssl-dev libcmocka-dev expect guile-2.0-dev libtasn1-6-dev libidn2-0-dev gawk gperf libunbound-dev dns-root-data bison help2man gtk-doc-tools texinfo texlive texlive-generic-recommended texlive-extra-utils build-essential bison flex cmake pkg-config libglib2.0-dev libpcap0.8-dev libgpgme11 libgpgme-dev doxygen libuuid1 uuid-dev libsql-translator-perl xmltoman sqlite3 libxml2-dev libxslt1.1 libxslt1-dev xsltproc libmicrohttpd-dev libpcap-dev pkg-config libgpgme11-dev uuid-dev sqlfairy xmltoman doxygen libssh-dev libksba-dev libldap2-dev libsqlite3-dev libmicrohttpd-dev clang rsync rpm nsis alien  libhiredis-dev libgcrypt11-dev libgnutls28-dev redis-server texlive-latex-base texlive-latex-recommended linux-headers-$(uname -r) -y

#
# Let's update the IANA Services Names list DB pórts.
#
    wget http://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xml
#
    openvas-portnames-update service-names-port-numbers.xml
#
    rm service-names-port-numbers.xml


#
# Let's complete the initial setup of Openvas and start the OMP console
#
    sudo openvas-feed-update && gsad && openvasmd --rebuild && openvas-setup && openvas-check-setup && service openvas-scanner start && openvas-start

#
If all is OK you are seeing the password of the admin user, you just see 2 or 3 warnings in your terminal,go ahead
#
# Now enjoy the power of this tool, in the OMP console.

#
#
#
Just in case that the console not open automatically, Let's start the console of openvas follow this steps:
#
#
    sudo openvasmd
#
    sudo openvassd

#
    sudo openvas-start
#
https://127.0.0.1:9392/omp

If you like indentify the ports in use by openvas use this command 
#
    sudo netstat -antp

#
#
# by    ҉αkα x⠠⠵
