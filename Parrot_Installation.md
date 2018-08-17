Manual for install and start openvas in Parrot Security OS
#
#
#
Tested on Linux parrot 4.17.0-parrot8-amd64 #1 SMP Parrot 4.17.8-1parrot8 (2018-08-11) x86_64 GNU/Linux
#
Distributor ID:	Parrot
#
#Description:	Parrot 4.2
#
Release:	4.2
#
Codename:	stable

If you like learn in detail about this arsenal just visit https://www.greenbone.net/


#
Let's install the pre-requisites.
#
sudo apt-get install build-essential bison flex cmake pkg-config libglib2.0-dev libpcap0.8-dev libgpgme11 libgpgme-dev doxygen libuuid1 uuid-dev libsql-translator-perl xmltoman sqlite3 libxml2-dev libxslt1.1 libxslt1-dev xsltproc libmicrohttpd-dev libpcap-dev pkg-config libgpgme11-dev uuid-dev sqlfairy xmltoman doxygen libssh-dev libksba-dev libldap2-dev libsqlite3-dev libmicrohttpd-dev clang rsync rpm nsis alien  libhiredis-dev libgcrypt11-dev libgnutls28-dev redis-server texlive-latex-base texlive-latex-recommended linux-headers-$(uname -r) -y

#
Let's update the IANA Services Names list DB pórts.
#
wget http://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xml
#
openvas-portnames-update service-names-port-numbers.xml
#
rm service-names-port-numbers.xml


#
Let's complete the initial setup of Openvas and start the OMP console
#
sudo openvas-feed-update && gsad && openvasmd --rebuild && openvas-setup && openvas-check-setup && service openvas-scanner start && openvas-start

#
If all is OK tou are seeing the passwword of the admin user, you just see 2 or 3 warnings in your terminal 
#
And you now enjoy in the OMP console seeing the power of this tool.

#
#
#
Just in case that the console not open automatically, follow this steps:
#
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

#
#
Bye!
