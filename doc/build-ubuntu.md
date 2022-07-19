Copyright (c) 2009-2013 The Bitcoin developers
Copyright (c) 2018-2022 The Suacoin Developers

Distributed under the MIT/X11 software license, see the accompanying
file COPYING or http://www.opensource.org/licenses/mit-license.php.
This product includes software developed by the OpenSSL Project for use in the [OpenSSL Toolkit](http://www.openssl.org/). This product includes
cryptographic software written by Eric Young ([eay@cryptsoft.com](mailto:eay@cryptsoft.com)), and UPnP software written by Thomas Bernard.

UBUNUT BUILD NOTES
====================

To Build
-------------------------
Assuming Ubuntu 14.04-LTS

Preparation
-----------

```
sudo apt-get update

sudo apt-get install build-essential libtool autotools-dev autoconf pkg-config libssl-dev
sudo apt-get install libboost-all-dev libminiupnpc-dev

```

Download suacoin source code
----------------------------
```
cd ~
git clone https://github.com/suacoin/suacoin.git
```

Berkley DB 4.8
--------------
```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install -y libdb4.8-dev libdb4.8++-dev
```

Compile Suacoin
---------------
```
cd ~/suacoin/src/
make -f makefile.unix
sudo ./suacoind /usr/bin
```

Run Suacoin Daemon
------------------
```
suacoind
```

