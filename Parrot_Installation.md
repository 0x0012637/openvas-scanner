https://www.greenbone.net/

sudo apt-get install build-essential bison flex cmake pkg-config libglib2.0-dev libpcap0.8-dev libgpgme11 libgpgme-dev doxygen libuuid1 uuid-dev libsql-translator-perl xmltoman sqlite3 libxml2-dev libxslt1.1 libxslt1-dev xsltproc libmicrohttpd-dev libpcap-dev pkg-config libgpgme11-dev uuid-dev sqlfairy xmltoman doxygen libssh-dev libksba-dev libldap2-dev libsqlite3-dev libmicrohttpd-dev clang rsync rpm nsis alien  libhiredis-dev libgcrypt11-dev libgnutls28-dev redis-server texlive-latex-base texlive-latex-recommended linux-headers-$(uname -r) -y


Make temporary directory to d/l source, extract and compile

cd ~

mkdir openvas

cd openvas

# Download Source
wget http://wald.intevation.org/frs/download.php/2351/openvas-libraries-8.0.8.tar.gz

wget http://wald.intevation.org/frs/download.php/2367/openvas-scanner-5.0.7.tar.gz

wget http://wald.intevation.org/frs/download.php/2359/openvas-manager-6.0.9.tar.gz

wget http://wald.intevation.org/frs/download.php/2363/greenbone-security-assistant-6.0.11.tar.gz

wget http://wald.intevation.org/frs/download.php/2332/openvas-cli-1.4.4.tar.gz

wget http://nmap.org/dist/nmap-5.51.6.tgz

# Extract packages

tar xvf greenbone-security-assistant-6.0.11.tar.gz

tar xvf openvas-libraries-8.0.8.tar.gz

tar xvf openvas-scanner-5.0.7.tar.gz

tar xvf openvas-cli-1.4.4.tar.gz 

tar xvf nmap-5.51.6.tgz

# Compile and install packages

#
cd openvas-libraries-8.0.8

cmake .

make

make doc

make install

cd ..
#

cd openvas-manager-6.0.9/

cmake .

make

make doc

make install

cd ..
#

cd openvas-scanner-5.0.7/

cmake .

make

make doc

make install

cd ..
#

cd openvas-cli-1.4.4/

cmake .

make

make doc

make install

cd ..
#

cd greenbone-security-assistant-6.0.11/

cmake .

make

make doc

make install

cd ..
#

cd nmap-5.51.6

./configure

make

make install

cd ..
#

ldconfig


#
sudo apt-get install openvas -y
#
Verify that the components are already instaleld
openvassd --version

openvasmd --version

sudo openvasmd --create-user=admin --role=Admin && openvasmd --user=admin --new-password=yourpw

sudo greenbone-scapdata-sync

sudo greenbone-certdata-sync

sudo gsad

openvasmd --rebuild

redis-cli flushall

sudo openvas-setup && openvas-scapdata-sync && openvas-certdata-sync && openvas-check-setup && openvas-stop 

#
Well we have the prerequisites now let's verify that everything is in order with this command 

#
sudo openvas-check-setup --v9

#
If all is OK and you just see 2 or 3 warnings

Is time to start the servicies of openvas

sudo openvasmd

sudo openvassd

#
Let's start the console of openvas

sudo openvas-start

https://127.0.0.1:9392/omp

If you like indentify the ports in use by openvas use this command 

sudo netstat -antp



Tested on Linux kp1 4.17.0-parrot8-amd64 #1 SMP Parrot 4.17.8-1parrot8 (2018-08-11) x86_64 GNU/Linux

Distributor ID:	Parrot
Description:	Parrot 4.2
Release:	4.2
Codename:	stable

