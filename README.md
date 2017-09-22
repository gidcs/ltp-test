# ltp-test

## Build and install ltp

```
# update packages lists
sudo apt-get update

# install build-essential, git, make-3.80+, bison-2.4.1+, Berkeley yacc, flex, autoconf-2.61+ & automake-1.10+
sudo apt-get install build-essential git make bison byacc flex autoconf automake libtool -y

# install tools and libraries that will be used
sudo apt-get install xfsprogs quota libkeyutils-dev libnuma-dev libcap-dev numactl exfat-utils btrfs-tools sysstat libaio-dev expect -y

# for dhcp test
sudo apt-get install isc-dhcp-server -y

# build LTP
git clone https://github.com/linux-test-project/ltp
cd ltp
make distclean
make autotools
./configure
make all -j4
sudo make install
```

## runtest

```
git clone https://github.com/gidcs/ltp-test.git
cd ltp-test
./runtest io
./runtest mem
./runtest net #please update netconf.env
```
