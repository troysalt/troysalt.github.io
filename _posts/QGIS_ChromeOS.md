### Install QGIS on a Chromebook
As Chromebooks become more powerful devices, they're becoming more capable of running intensive applications. With Linux (beta), the doors are open to many open-source programs. A couple of years ago, I never thought I would be running GIS analysis on my Chromebook, but here we are today.

### Prerequisites

- Linux (beta) needs to be installed on your Chromebook. This is a relatively straight-forward process, for instructions, see [this Google support page](https://support.google.com/chromebook/answer/9145439?hl=en).
- I would recommend at least a Core m3 processor, 8 GB of RAM, and 64 GB of storage. *You can install QGIS on lesser machines, but the you'll likely have issues with large data sets*. I've installed QGIS on both a Pixel Slate (m3 7th gen, 8 GB of RAM, 64 GB of storage) and an HP X2 (m3 8th gen, 4 GB of RAM, 32 GB of storage).
- Either know the Linux terminal, or be ready to learn something completely new. You can always change your mind on Linux by uninstalling Linux through the settings.
- Know that Linux in ChromeOS currently runs on Debian 9 (codenamed "stretch") as of December 2019. However, there are rumors a future release may include Debian 10 ("buster"). This is important when you choose the package you're installing.

### Installing QGIS

If you don't care what version you get, then installation is very simple. Just open the Terminal app (in the app drawer, under the "Linux Apps" folder), and type the following commands.

    sudo apt-get update
    sudo apt-get upgrade
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
- 'esc'


<!--stackedit_data:
eyJoaXN0b3J5IjpbNjQ1NjI0NDc1LC0xNzM1MTIxNDY4LC0xMj
MwOTQ0MTg2LC0xMjQ1NDk0NTQwXX0=
-->