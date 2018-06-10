# Wisp Wallet

This is the repository of the "Wisp" wallet for Spectrecoin. For more info, see https://github.com/wispproject/doc/wiki

## Building

These build instructions apply to Unix systems; For Windows build instructions please visit our Discord.

### Dependencies

Debian/Ubuntu/Mint:
* `apt-get install build-essential libssl-dev libevent-dev libseccomp-dev libcap-dev pkg-config autoconf libtool`

Fedora/Red Hat/CentOS:
* `dnf install git autoconf automake qt5-qtbase-devel openssl-devel libevent-devel libseccomp-devel libcap-devel libtool boost-devel qt5-linguist qt5-qtwebengine-devel`

Arch Linux:
* `pacman -S --needed base-devel openssl libevent libseccomp libcap boost qt5`

Mac OS X (using the [Homebrew](https://brew.sh/) package manager)
```
brew install autoconf automake libtool pkg-config openssl@1.1 libevent boost gcc wget
brew tap KDE-mac/homebrew-kde
brew install qt
```

### Compilation

```
git clone https://github.com/wispproject/wallet wisp
cd wisp
./autogen.sh
./configure --enable-gui  # leave out --enable-gui to build only the console wallet
make -j2  # use a higher number if you have many cores and memory, leave -j2 out if you are on a very low-powered system like Raspberry Pi
```

### Running Wisp

`./src/spectre`

You can also copy this binary to `/usr/local/bin` for a system-wide installation for example.

If these instructions don't work for you, please open an issue or report it in Discord so we can fix the instructions.
