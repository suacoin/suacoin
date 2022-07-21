Copyright (c) 2009-2013 The Bitcoin developers
Copyright (c) 2018-2022 The Suacoin Developers

Distributed under the MIT/X11 software license, see the accompanying
file COPYING or http://www.opensource.org/licenses/mit-license.php.
This product includes software developed by the OpenSSL Project for use in the [OpenSSL Toolkit](http://www.openssl.org/). This product includes
cryptographic software written by Eric Young ([eay@cryptsoft.com](mailto:eay@cryptsoft.com)), and UPnP software written by Thomas Bernard.

UBUNTU BUILD NOTES
====================

To Build
-------------------------
Assuming Ubuntu 20

Preparation
-----------

```
sudo apt-get update

sudo apt-get install libboost-all-dev
sudo apt-get install build-essential libtool autotools-dev autoconf pkg-config libssl-dev
sudo apt-get install libminiupnpc-dev
wget http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz
tar -xvf db-4.8.30.NC.tar.gz
sed -i ‘s/__atomic_compare_exchange/__atomic_compare_exchange_db/g’ db-4.8.30.NC/dbinc/atomic.h
cd db-4.8.30.NC/build_unix
mkdir -p build
../dist/configure --prefix=/usr/local --enable-cxx --with-pic
make
sudo make install
sudo cp -rf build/include/* /usr/include
cd ../../
wget https://ftp.openbsd.org/pub/OpenBSD/LibreSSL/libressl-3.1.5.tar.gz
tar xvfz libressl-3.1.5.tar.gz
cd libressl-3.1.5
./configure --prefix=/usr/local/libressl --with-openssldir=/usr/local/libressl && make && sudo make install
sudo rm -rf /usr/include/openssl/*
sudo cp -rf include/openssl/* /usr/include/openssl/
sudo cp -rf lib/* /usr/lib/x86_64-linux-gnu
cd ..
git clone https://github.com/suacoin/suacoin.git
cd suacoin/src/
make -f makefile.unix
sudo cp suacoind /usr/bin/




Run Suacoin Daemon
------------------
```
suacoind
```

