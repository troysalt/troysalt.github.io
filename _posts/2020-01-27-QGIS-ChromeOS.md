---
layout: post
title: How to Install QGIS on a Chromebook
gh-repo: troysalt.github.io
gh-badge: [star, fork, follow]
tags: [QGIS, linux, debian]
comments: true
---

As Chromebooks become more powerful devices, they're becoming more capable of running intensive applications. With Linux (beta), the doors are open to many open-source programs. A couple of years ago, I never thought I would be running GIS analysis on my Chromebook, but here we are today.

### Prerequisites

- I would recommend at least a Core m3 processor, 8 GB of RAM, and 64 GB of storage. *You can install QGIS on lesser machines, but the you'll likely have issues with large data sets*. I've installed QGIS on both a Pixel Slate (m3 8th gen, 8 GB of RAM, 64 GB of storage) and an HP X2 (m3 7th gen, 4 GB of RAM, 32 GB of storage).
- Either know the Linux terminal, or be ready to learn something completely new. You can always change your mind on Linux by uninstalling Linux through the settings.

**If you have not installed Linux yet:**

- As of Feburary 2020, most Chromebooks default to a version of Linux called Debian 9 ("stretch"). However, with ChromeOS 80, there is a new flag which will install Debian 10 ("buster"). To get the latest install of QGIS, you'll want to make sure this flag is enabled (type chrome://flags in a new tab, and search for "buster", then make sure the "New Crostini containers use Buster" flag is enabled).
- Now you're ready to install Linux (beta) on your chromebook. This is a relatively straight-forward process, for instructions, see [this Google support page](https://support.google.com/chromebook/answer/9145439?hl=en).

**If you have already installed Linux:**

- If you are not sure what version you have, open the Terminal app and type: cat /etc/issue and press enter. It should say Debian GNU/ Linux 10 (or 9).
- If you want QGIS 3.10, you'll need to be on Debian 10. Otherwise, you'll get QGIS 3.4.
- You can manually upgrade from Debian 9 to 10. Before proceeding, I recommend backing up your Linux container through the ChromeOS settings, just in case anything goes wrong. 
- To upgrade follow the instructions on [this reddit post](https://www.reddit.com/r/Crostini/comments/9rhauo/upgrade_from_stretch_to_buster_compilation_of/?ref=share&ref_source=embed&utm_content=title&utm_medium=post_embed&utm_name=7ea9b5b4d8ee49bc9a7501dc0cc3df15&utm_source=embedly&utm_term=9rhauo). Note that you should only need to execute the first code block, I had no issues with the ChromeOS files app (the Reddit post was written before the ChromeOS team polished things).

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
- 'esc' and type ':q!' to exit and discard changes

Add the following text to the last two lines and save and exit the Apt sources list.

    deb https://qgis.org/debian buster main
    deb-src https://qgis.org/debian buster main

Now run the same commands from earlier:

    sudo apt update
    sudo apt upgrade

If you get the following error, there is a mistake in your Apt source list. Double-check that you entered everything correctly.

    E: Malformed entry 5 in list file /etc/apt/sources.list (Component)
    E: The list of sources could not be read.

Before we can install QGIS, you'll need to add the repository key. In the terminal, copy and paste the following (remember to use ctrl+shift+v).

    wget -O - https://qgis.org/downloads/qgis-2019.gpg.key | gpg --import gpg --fingerprint 51F523511C7028C3

This should output:

    pub   rsa4096 2019-08-08 [SCEA] [expires: 2020-08-08] 8D5A 5B20 3548 E500 4487  DD19 51F5 2351 1C70 28C3
    uid           [unknown] QGIS Archive Automatic Signing Key (2019) <qgis-developer@lists.osgeo.org>

Now copy and paste this to the terminal:

    gpg --export --armor 51F523511C7028C3 | sudo apt-key add -

Let's make sure we've done everything correctly, and that our repository has the latest release.

    apt-cache policy qgis

This will output a few things, we're just interested one part.

    Installed: 1:3.10.2+15buster
    Candidate: 1:3.10.2+15buster
  
This confirms we installed QGIS 3.10. If you see a different version, something went wrong.

Enjoy!

Please [contact me](https://troysalt.github.io/contact/) for any questions, comments, insights, or corrections.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNzgzMTIwODAsLTUyMDE1ODQ2MCw3Nj
EwNzI0NTEsOTI3MjYyMjQxXX0=
-->
