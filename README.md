# libimobiledevice-win64
Compile libimobiledevice with windows MSYS2.

## Installation / Getting started

### MSYS2 / windows10
First install [MSYS2](https://msys2.github.io/) launch mingw64.exe

Next all required dependencies and build tools:
```shell
pacman -S mingw-w64-x86_64-libzip mingw-w64-x86_64-toolchain mingw-w64-x86_64-autotools git
```
Then clone the actual project repository:
```shell
git clone https://github.com/libimobiledevice/libplist.git
git clone https://github.com/libimobiledevice/libimobiledevice-glue.git
git clone https://github.com/libimobiledevice/libusbmuxd.git
git clone https://github.com/libimobiledevice/libimobiledevice.git
git clone https://github.com/libimobiledevice/ideviceinstaller.git
git clone https://github.com/libimobiledevice/libideviceactivation.git
git clone https://github.com/libimobiledevice/libirecovery.git
git clone https://github.com/libimobiledevice/idevicerestore.git
```
Build and install in the respective actual project repository.
```shell
cd libplist
./autogen.sh
make
make install
cd ../libimobiledevice-glue
./autogen.sh
make
make install
cd ../libusbmuxd
./autogen.sh
make
make install
cd ../libimobiledevice
./autogen.sh
make
make install
cd ../ideviceinstaller
./autogen.sh
make
make install
```
An executable file will be generated in C:\msys64\mingw64\bin
