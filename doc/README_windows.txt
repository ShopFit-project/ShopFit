ShopFit integration/staging tree
================================

http://www.shopfit.ro

Copyright (c) 2019 ShopFit Developers

What is ShopFit?
----------------
X15
PoS Minimum - 24 Hours
PoS Maximum - Unlimited
PoS Interest - 7% Annually 
1 Minute Target Spacing
6 Blocks for Full Confirmation
Difficulty Retargets Every Block
100,000,000 Total Coins

P2P Port = 11089
RPC Port = 21089
Testnet Port = 31089

For more information, as well as an immediately useable, binary version of
the ShopFit client sofware, see http://www.shopfit.ro

Build Instructions for QT4 Linux Wallet
======================================
Create a folder named ShopFit in /home/ and unpack the contents of ~/ShopFit-master to that folder.

Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt5-default qttools5-dev-tools qt-sdk make qrencode libqrencode-dev

//In terminal navigate to the ShopFit folder.

$ cd /home/ShopFit

//Enter into the terminal:

$ qmake -qt=qt4 "USE_QRCODE=1" "USE_UPNP=-"

//Then:

$ make

This will compile and build the QT Wallet which takes a little while, please be patient.

When finished you will have a file called ShopFit-QT - Simply Double Click

//end of guide

Build Instructions for QT5 Linux Wallet
======================================
Create a folder named ShopFit in /home/ and unpack the contents of ~/ShopFit-master to that folder.

Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt5-default qttools5-dev-tools qt-sdk make qrencode libqrencode-dev

//In terminal navigate to the ShopFit folder.

$ cd /home/ShopFit

//Enter into the terminal:

$ qmake -qt=qt5 "USE_QRCODE=1" "USE_UPNP=-"

//Then:

$ make

This will compile and build the QT Wallet which takes a little while, please be patient.

When finished you will have a file called ShopFit-QT - Simply Double Click

//end of guide

Build Instructions for QT4 Linux Wallet
======================================
Create a folder named ShopFit in /home/ and unpack the contents of ~/ShopFit-master to that folder.

Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt-sdk make qrencode libqrencode-dev

//In terminal navigate to the ShopFit folder.

$ cd /home/ShopFit

//Enter into the terminal:

$ qmake -qt=qt4 "USE_QRCODE=1" "USE_UPNP=-"

//Then:

$ make

This will compile and build the QT Wallet which takes a little while, please be patient.

When finished you will have a file called ShopFit-QT - Simply Double Click

//end of guide


Build Instructions for Terminal Based Linux Wallet
===================================================
//Create a folder named ShopFit in /home/ and unpack the contents of ~/ShopFit-master to that folder.

//Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt-sdk make 

//In terminal navigate to the ShopFit folder.

$ cd /home/ShopFit

//Enter into the terminal:

$ make -f makefile.unix "USE_UPNP=-"

//This will produce a file named ShopFitd which is the command line instance of ShopFit-qt

//Now type:

$ strip ShopFitd

//When finished you will have a file called ShopFitd

//To run ShopFit

$ ./ShopFitd & 

//It will complain about having no ShopFit.conf file, we'll edit the one provided and move it into place

$ cd ..
$ nano ShopFit.conf

//Edit the Username and Password fields to anything you choose (but remember them) then save the file

$ mv ShopFit.conf /home/ShopFit/src/
$ cd src/
$ ./ShopFitd &

//The server will start. Here are a few commands, google for more.

$ ./ShopFitd getinfo
$ ./ShopFitd getmininginfo
$ ./ShopFitd getnewaddresss

//end of guide


License
-------

ShopFit is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the ShopFit
development team members simply pulls it.

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/ShopFit-project/ShopFit) are created
regularly to indicate new official, stable release versions of ShopFit.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake SteemX1_QT_TEST=1 -o Makefile.test ShopFit-qt.pro
    make -f Makefile.test
    ./ShopFit-qt_test





