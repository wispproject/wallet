# Wisp Wallet

This is the repository of the official Wisp wallet. For more info, see https://github.com/wispproject/doc/wiki

# Building

**Note:** Please don't try to install third-party libraries on your Linux system manually. You should always use the package manager if possible. The following instructions will show you how to build Wisp on your Linux system using packages from your package manager.

## Dependencies

### Debian 9 "Stretch", Ubuntu 18.04 LTS, Linux Mint 19

**Note**: The Qt wallet currently crashes on Debian due to [bug #33](https://github.com/spectrecoin/spectre/issues/33). Ubuntu and Mint work. On Debian you can use the headless version (wispd) until the bug gets resolved.

For GUI and headless, as root: 
* `apt-get install --no-install-recommends git autoconf automake libtool pkg-config g++ lib{ssl,event,z,boost{,-{system,chrono,filesystem,program-options,thread,iostreams}},cap,seccomp}-dev make`

For GUI (additionally), as root: 
* `apt-get install --no-install-recommends qtbase5-dev libqt5webchannel5-dev qtwebengine5-dev qttools5-dev-tools qt5-default`

### Fedora, Red Hat, CentOS

For GUI and headless, as root: 
* `dnf install git autoconf automake openssl-devel libevent-devel libseccomp-devel libcap-devel libtool boost-devel`

For GUI (additionally), as root: 
* `dnf install qt5-qtbase-devel qt5-linguist qt5-qtwebengine-devel`

### Mac OS X

Using the [Homebrew](https://brew.sh/) package manager:
```
brew install autoconf automake libtool pkg-config openssl@1.1 libevent boost gcc wget
brew tap KDE-mac/homebrew-kde
brew install qt
```

## Setup
For GUI and headless, as user:
```
mkdir ~/build
cd ~/build
git clone https://github.com/wispproject/wallet wisp
cd wisp
./autogen.sh
```

## Configure
For headless, as user:
* `./configure`

For GUI, as user:
* `./configure --enable-gui`

## Make
For GUI and headless, as user:
* `make`

## Install

For headless, as root:
* `cp src/wispd /usr/local/bin/`

For GUI, as root:
* `cp src/wisp /usr/local/bin/`

# Usage

You can now start the Wisp Qt wallet using the "wisp" command. For the Wisp daemon (wispd), please refer to the general Bitcoin usage instructions:

* https://en.bitcoin.it/wiki/Running_Bitcoin
* https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_calls_list
