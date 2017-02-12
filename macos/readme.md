# MacOS Build Instructions for Zeal60 Command Line Tool

In order to get started, you'll need both this repo, as well as the qmk-firmware repo

```
cd ~
git clone --recursive https://github.com/Wilba6582/zeal60
git clone https://github.com/qmk/qmk_firmware
```

You'll also need the HID API, Fox Toolkit (needs XQuartz) and LibUSB (using [Homebrew](https://homebrew.sh):

```
brew cask install xquartz
brew install hidapi fox libusb libtool automake
```

Now compile HIDUSB:

```
cd ~/zeal60/hidapi
./bootstrap
./configure
make
sudo make install
cd ..
```

The enter the dir for the makefile:

`cd ~/zeal60/zeal60`

And run `make` in order to compile: 

`make`

The results should be similar to the following: 

```
g++ -o zeal60 -lhidapi zeal60.cpp keycode.cpp -Wno-write-strings -Wno-pragma-once-outside-header
```

And to test it out: 

```
./zeal60
```
