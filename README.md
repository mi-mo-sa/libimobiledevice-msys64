# libimobiledevice-msys64
Compile [libimobiledevice](https://github.com/libimobiledevice) with windows MSYS2.

## Usage

Documentation about using the library in your application is not available yet.
The "hacker way" for now is to look at the implementation of the included
utilities.

### Utilities

The library bundles the following command-line utilities in the tools directory:

| Utility                    | Description                                                        |
| -------------------------- | ------------------------------------------------------------------ |
| `idevice_id`               | List attached devices or print device name of given device         |
| `idevicebackup`            | Create or restore backup for devices (legacy)                      |
| `idevicebackup2`           | Create or restore backups for devices running iOS 4 or later       |
| `idevicecrashreport`       | Retrieve crash reports from a device                               |
| `idevicedate`              | Display the current date or set it on a device                     |
| `idevicedebug`             | Interact with the debugserver service of a device                  |
| `idevicedebugserverproxy`  | Proxy a debugserver connection from a device for remote debugging  |
| `idevicediagnostics`       | Interact with the diagnostics interface of a device                |
| `ideviceenterrecovery`     | Make a device enter recovery mode                                  |
| `ideviceimagemounter`      | Mount disk images on the device                                    |
| `ideviceinfo`              | Show information about a connected device                          |
| `idevicename`              | Display or set the device name                                     |
| `idevicenotificationproxy` | Post or observe notifications on a device                          |
| `idevicepair`              | Manage host pairings with devices and usbmuxd                      |
| `ideviceprovision`         | Manage provisioning profiles on a device                           |
| `idevicescreenshot`        | Gets a screenshot from the connected device                        |
| `idevicesetlocation`       | Simulate location on device                                        |
| `idevicesyslog`            | Relay syslog of a connected device                                 |
| `ideviceinstaller`         | Interact with the app installation service of an iOS device        |

## How to Build

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
