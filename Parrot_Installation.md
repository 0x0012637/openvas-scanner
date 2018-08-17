https://www.greenbone.net/

sudo apt-get install build-essential bison flex cmake pkg-config libglib2.0-dev libpcap0.8-dev libgpgme11 libgpgme-dev doxygen libuuid1 uuid-dev libsql-translator-perl xmltoman sqlite3 libxml2-dev libxslt1.1 libxslt1-dev xsltproc libmicrohttpd-dev libpcap-dev pkg-config libgpgme11-dev uuid-dev sqlfairy xmltoman doxygen libssh-dev libksba-dev libldap2-dev libsqlite3-dev libmicrohttpd-dev clang rsync rpm nsis alien  libhiredis-dev libgcrypt11-dev libgnutls28-dev redis-server texlive-latex-base texlive-latex-recommended linux-headers-$(uname -r) -y


#
sudo openvas-setup && openvas-feed-update && openvas-scapdata-sync && openvas-certdata-sync && openvasmd --rebuild && openvas-check-setup


#
If all is OK and you just see 2 or 3 warnings
#
Is time to start the servicies of openvas
#
sudo openvasmd
#
sudo openvassd

#
Let's start the console of openvas
#
sudo openvas-start
#
https://127.0.0.1:9392/omp

If you like indentify the ports in use by openvas use this command 
#
sudo netstat -antp



Linux parrot 4.17.0-parrot8-amd64 #1 SMP Parrot 4.17.8-1parrot8 (2018-08-11) x86_64 GNU/Linux
#
Distributor ID:	Parrot
#
Description:	Parrot 4.2
#
Release:	4.2
#
Codename:	stable
