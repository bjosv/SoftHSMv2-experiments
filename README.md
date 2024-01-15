# SoftHSMv2 experiments

## Dependencies

```
> Build (gives libbotan 2.19 currently)
sudo apt-get -y install botan libbotan-2-dev libp11-kit-dev
(or/and p11-kit)

> Tests
sudo apt-get -y install libcppunit-dev
(or/and libcppunit-1.15-0)
```

## Build

### Using openssl

```
> or run: `openssl version`
  OpenSSL 1.1.1u  30 May 2023
> or run: `openssl version -d`
  OPENSSLDIR: "/usr/local/ssl"
Not working? Might require ~3.0

./configure
```

### Using botan

```
./configure --with-crypto-backend=botan
```

### Own openssl

```
wget https://www.openssl.org/source/openssl-3.0.12.tar.gz
./config --prefix=$HOME/tmp/openssl --openssldir=$HOME/tmp/openssl
make
make test
make install

./configure --with-crypto-backend=openssl --with-openssl=$HOME/tmp/openssl
make
make check
```

## Issues

### Build issues:
https://github.com/opendnssec/SoftHSMv2/issues/718
