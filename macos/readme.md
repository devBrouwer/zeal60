# MacOS Build Instructions for Zeal60 Command Line Tool

In order to get started, you'll need both this repo, as well as the qmk-firmware repo

```
cd ~
git clone https://github.com/Wilba6582/zeal60
git clone https://github.com/qmk/qmk_firmware
```

You'll also need the HID API (using [Homebrew](https://homebrew.sh):

`brew install hidapi`

Now copy the hidapi.h file to the correct folder:

`cp /usr/local/Cellar/hidapi/0.8.0-rc1/include/hidapi/hidapi.h ~/zeal60/hidapi`

The enter the dir for the makefile:

`cd zeal60/zeal60`

And run `make` in order to compile: 

`make`

The results should be similar to the following: 

```
g++ -o zeal60 -lhidapi zeal60.cpp keycode.cpp -Wno-write-strings -Wno-pragma-once-outside-header
```

And to test it out: 

```
./zeal60
*** Error: Device not found
```
