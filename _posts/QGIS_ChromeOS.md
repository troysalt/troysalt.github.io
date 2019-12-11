### Install QGIS on a Chromebook
As Chromebooks become more powerful devices, they're becoming more capable of running intensive applications. With Linux (beta), the doors are open to many open-source programs. A couple of years ago, I never thought I would be running GIS analysis on my Chromebook, but here we are today.

### Prerequisites

- Linux (beta) needs to be installed on your Chromebook. This is a relatively straight-forward process, for instructions, see [this Google support page](https://support.google.com/chromebook/answer/9145439?hl=en).
- I would recommend at least a Core m3 processor, 8 GB of RAM, and 64 GB of storage. *You can install QGIS on lesser machines, but the you'll likely have issues with large data sets*. I've installed QGIS on both a Pixel Slate (m3 7th gen, 8 GB of RAM, 64 GB of storage) and an HP X2 (m3 8th gen, 4 GB of RAM, 32 GB of storage).
- Either know the Linux terminal, or be ready to learn something completely new. You can always change your mind on Linux by uninstalling Linux through the settings.
- Know that Linux in ChromeOS currently runs on Debian 9 (codenamed "stretch") as of December 2019. However, there are rumors a future release may include Debian 10 ("buster"). This is important when you choose the package you're installing.

### Installing QGIS

If you don't care what version you get, then installation is very simple. Just open the Terminal app (in the app drawer, under the "Linux Apps" folder), and type the following commands.

    sudo apt update
    sudo apt upgrade
    sudo apt-get install QGIS

Unfortunately this installs version 2.14 "Essen".  This version was released almost 4 years ago, so we'll have to add another repository to the [Apt sources list](https://wiki.debian.org/SourcesList) to get the latest version. This may be a bit intimidating, so please follow the instructions carefully.

First, enter the Apt sources list:

    sudo vi /etc/apt/sources.list

This will take you to the vi text editor. You should see two standard repositories in this list.  To use the vi editor, you'll need to know some commands:

- 'shift + g' will move the cursor to the end of the line
- 'o' will add a new line and switch to insert mode
- 'ctrl + shift + v' will paste text
- 'esc' will exit insert mode
- ':wq' + 'enter' will save and exit the Apt sources list
- 'esc' and type ':q!' if you think you messed up

Add the following text to the last line and save and exit the Apt sources list.

    deb https://qgis.org/debian stretch main
    deb-src https://qgis.org/debian stretch main

Now run the same commands from earlier:

    sudo apt update
    sudo apt upgrade

If you get the following error, there is a mistake in your Apt source list.

    E: Malformed entry 5 in list file /etc/apt/sources.list (Component)
    E: The list of sources could not be read.

Before we can install QGIS, you'll need to add the repository key. In the terminal, copy and paste the following (remember to use ctrl+shift+v).

    wget -O - https://qgis.org/downloads/qgis-2019.gpg.key | gpg --import gpg --fingerprint 51F523511C7028C3

This should output:

    pub   rsa4096 2019-08-08 [SCEA] [expires: 2020-08-08] 8D5A 5B20 3548 E500 4487  DD19 51F5 2351 1C70 28C3
    uid           [unknown] QGIS Archive Automatic Signing Key (2019) <qgis-developer@lists.osgeo.org>

Now copy and past this to the terminal:

    gpg --export --armor 51F523511C7028C3 | sudo apt-key add -

Let's make sure our repository has the latest release.

    sudo apt search qgis-common

This will output a few things, we're just interested one part.

    qgis-common/stretch,now 1:3.4.4+14stretch all [installed,automatic] QGIS - architecture-independent data
  
You'll notice the 3.4.4+14, if you see a different version, something went wrong. This is the version of QGIS in the repository, and is the latest Long Term Release (LTR). 

Note that there is a newer version of QGIS (3.10.X). 
<!--stackedit_data:
eyJoaXN0b3J5IjpbODMxOTQxMzk1LC0xNzM1MTIxNDY4LC0xMj
MwOTQ0MTg2LC0xMjQ1NDk0NTQwXX0=
-->