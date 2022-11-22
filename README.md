# MCCI Cricket UI Releases

This collection of repositories is used for building the MCCI `Cricket` UI for MCCI USB Switches. Complete releases are also available [here](https://github.com/mcci-usb/COLLECTION-cricket-ui/releases).

<!-- TOC depthFrom:2 updateOnSave:true -->

- [Installing Sources](#installing-sources)
- [Prerequisites for running or building](#prerequisites-for-running-or-building)
- [Interpret python source](#interpret-python-source)
- [Cricket UI Exe maker](#Cricket-UI-Exe-maker)
- [Application Installer creation](#application-installer-creation)
- [Installation steps in Linux](#installation-steps-in-Linux)
- [Application release procedure](#application-release-procedure)
- [Meta](#Meta)

<!-- /TOC -->

## Installing Sources

<strong>From a tar file</strong>

Unpack the tar file in a convenient directory, using <code>tar -xzf <em><strong>tarfile.tgz</strong></em> -C <em><strong>destdir</strong></em></code>.

Then change directory to the <code><em><strong>destdir</strong></em></code>.

<strong>From github.mcci.com</strong>

Clone the release tag repository from MCCI's github server using the command:

```shell
git clone --recursive https://github.com/mcci-usb/COLLECTION-cricket-ui.git --branch <tag_name> --single-branch
```
For an example - Cloning for the release tag 'v1.0.0', replace the <tag_name> with v1.0.0 

Then change directories to the top level of the cloned repository.

## Prerequisites for running or building

<strong>On Windows:</strong>

Development environment

* OS - Windows 10 64 bit
* Python - 3.7.6
* wxpython - 4.0.7.post2
* pyserial - 3.4
* pyusb - 1.0.2
* libusb - 1.0.22b9
* libusb1 - 1.8
* pyinstaller - 4.7
* matplotlib -1.16.0

Download [python3.7.6](https://www.python.org/downloads/release/python-376/) and install

```shell
pip install wxpython==4.0.7.post2
pip install pyserial
pip install pyusb
pip install libusb
pip install libusb1
pip install matplotlib
pip install pyinstaller
```

<strong>On Linux:</strong>

Development environment

* Linux OS - Ubuntu 20.04 64 bit
* Python - 3.8.10
* wxpython - 4.0.7.post2
* pyserial - 3.4
* pyusb - 1.0.2
* libusb - 1.0.22b9
* libusb1 - 1.8
* pyinstaller - 4.7
* matplotlib - 3.5
* hidapi - 0.10.1  - Only for Mac OS

```shell
sudo apt-get install python3
sudo apt-get install python3-pip
sudo pip3 install wxpython==4.0.7.post2
sudo pip3 install pyserial
sudo pip3 install pyusb
sudo pip3 install libusb
sudo pip3 install libusb1
sudo pip3 install matplotlib
sudo pip3 install pyinstaller
brew install hidapi - Only for Mac OS
```

Note:
* If the installation of wxpython is not success, perform `sudo apt-get install build-essential libgtk-3-dev`
* Some times the installation of wxpython takes longer time (>30 minutes).

<strong>On Mac:</strong>

Development environment

* Mac OS - Mac OS - Cataina V10.15.7 64 bit
* Python - 3.7.0
* wxpython - 4.0.7.post2
* pyserial - 3.4
* pyusb - 1.0.2
* libusb - 1.0.22b9
* libusb1 - 1.8
* pyinstaller - 4.2
* matplotlib - 3.2.2
* hidapi - 0.10.1  - Only for Mac OS

```shell
sudo apt-get install python3
sudo apt-get install python3-pip
sudo pip3 install wxpython==4.0.7.post2
sudo pip3 install pyserial
sudo pip3 install pyusb
brew install libusb
sudo pip3 install libusb1
sudo pip3 install matplotlib
sudo pip3 install pyinstaller
brew install hidapi - Only for Mac OS
```

<strong>On RaspberryPI:</strong>

Development environment

* Raspberry Pi OS - aarch64 in Ubuntu 20.04 bit
* Python - 3.6.9
* wxgtk-4.0
* pyserial - 3.5
* pyusb - 1.1.1
* libusb - 1.0.23b7
* libusb1 - 1.9
* pyinstaller - 4.2
* matplotlib - 1.14.0
* hidapi - 0.10.1  - Only for Mac OS

```shell
sudo add-apt-repository ppa:swt-techie/wxpython4
sudo apt-get update
sudo apt-get install python3-wxgtk4.0
sudo pip3 install pyserial
sudo pip3 install pyusb
sudo pip3 install libusb
sudo pip3 install libusb1
sudo pip3 install matplotlib
sudo pip3 install pyinstaller
```

## Interpret python source

This is to ensure that the source can be interpreted without any error

Move to the directory `destdir/cricket/src/`

<strong>On Windows:</strong>

```shell
python main.py
```

This show up application UI window on screen

<strong>On Linux:</strong>

```shell
python3 main.py
```

This show up application UI window on screen

<strong>On Raspberry PI3:</strong>

```shell
python3 main.py
```

This show up application UI window on screen


<strong>On Mac:</strong>

```shell
python3.6 main.py
```

This show up application UI window on screen

## Cricket UI Exe maker

EXE is a file extension for an executable file format. It makes distributing Cricket UI much easier. The exe produced by PyInstaller is standalone.

<strong>On Windows:</strong>

Run `pyinstaller` Cmd in `exeScript` directory.

```shell
pyinstaller Cricket-Windows.spec
```
The executable 'Cricket' show up in `exeScriptdir/dist/Cricket/`.

<strong>On Linux and On Raspberry Pi:</strong>

Run `pyinstaller` Cmd in `exeScript` directory.

```shell
pyinstaller Cricket-Linux.spec
```
The executable 'Cricket' show up in `exeScriptdir/dist/`.

<strong>On Mac:</strong>

Run `pyinstaller` Cmd in `exeScript` directory.

```shell
pyinstaller Cricket-Mac.spec
```

The executable 'Cricket' show up in `exeScriptdir/dist/`.


## Application Installer creation

<strong>On Windows:</strong>

Download [Inno Setup Compiler](https://jrsoftware.org/isdl.php#stable) and install

Run the Inno Setup Script file 'Cricket-Windows' which is in `destdir/installerScript/`.

The App Installer 'cricket-<ver tag>-windows-installer' show up in `destdir/AppInstaller/`.


<strong>On Linux:</strong>

Create Linux deb package using Debreate Debian package builder

Run the Package project file 'Cricket-Linux' which is in `destdir/installerScript/`.

The App Installer 'cricket-<ver tag>-linux-installer' show up in `destdir/AppInstaller/`.

<strong>On Raspberry Pi:</strong>

Create Raspberry Pi deb package using Debreate Debian package builder

Run the Package project file 'Cricket-Linux' which is in `destdir/installerScript/`.

The App Installer 'cricket-<ver tag>-linux-installer' show up in `destdir/AppInstaller/`.

<strong>On Mac:</strong>

Download [Packages](http://s.sudre.free.fr/Software/Packages/about.html) and install

To know about [Packages](https://www.techrepublic.com/article/how-to-repackage-os-x-apps-with-packages/) more

Run the Package project file 'Cricket-Mac' which is in `destdir/installerScript/`.

The App Installer 'cricket-<ver tag>-mac-installer' show up in `destdir/AppInstaller/`.

## Installation steps in Linux

* download the MCCI Cricket UI Linux installer from Collections-cricket-ui releases.
* extract the Linux installer file.
* open the Terminal at .deb file location.
* install the Cricket_2.7.0_all.deb using the cmd of `sudo dpkg -i Cricket_2.7.0_all.deb`

## Application release procedure

<strong>On Windows:</strong>

Create a release directory with release version `MCCI-Cricket-UI-<ver tag>-Windows-Installer`

Move the App Installer 'cricket-<ver tag>-windows-installer' into the release directory and zip (compress) it, 
the name of zipped folder should be  `MCCI-Cricket-UI-<ver tag>-Windows-Installer.zip`.

The Application Installer must be digitally signed before it can be deployed.

<strong>On Linux:</strong>

Create a release directory with release version `MCCI-Cricket-UI-<ver tag>-Linux-Installer.deb`

Move the App Installer 'cricket-<ver tag>-windows-installer' into the release directory and zip (compress) it, 
the name of zipped folder should be  `MCCI-Cricket-UI-<ver tag>-Linux-Installer.tar.gz`.

The Application Installer must be digitally signed before it can be deployed.

<strong>On Raspberry Pi:</strong>

Create a release directory with release version `MCCI-Cricket-UI-<ver tag>-Linux-Installer.deb`

Move the App Installer 'cricket-<ver tag>-windows-installer' into the release directory and zip (compress) it, 
the name of zipped folder should be  `MCCI-Cricket-UI-<ver tag>-RPI-Linux-aarch64-Installer.tar.gz`.

The Application Installer must be digitally signed before it can be deployed.

<strong>On Mac:</strong>

Create a release directory with release version `MCCI-Cricket-UI-<ver tag>-Mac-Installer.pkg`.

Move the App Installer 'Cricket-Installer' into the release directory and zip (compress) it, 
the name of zipped folder should be `MCCI-Cricket-UI-<ver tag>-Mac-Installer.pkg.zip`.

The Mac application and the Application Installer must be signed and notarized before it can be deployed.

## Meta

### Copyright and License

Except as explicitly noted, content created by MCCI in this repository tree is copyright (C) 2021, MCCI Corporation.
  
The Cricket UI is released under the terms of the attached [GNU General Public License, version 2](./LICENSE.md). `LICENSE.md` is taken directly from the [FSF website](http://www.gnu.org/licenses/old-licenses/gpl-2.0.md).

Commercial licenses and commercial support are available from MCCI Corporation.

Git submodules are subject to their own copyrights and licenses; however overall collection is a combined work, and is copyrighted and subject to the overall license.

### Support Open Source Hardware and Software

MCCI invests time and resources providing this open source code, please support MCCI and open-source hardware by purchasing products from MCCI and other open-source hardware/software vendors!

For information about MCCI's products, please visit [store.mcci.com](https://store.mcci.com/).

### Trademarks

MCCI and MCCI Catena are registered trademarks of MCCI Corporation. All other marks are the property of their respective owners.
