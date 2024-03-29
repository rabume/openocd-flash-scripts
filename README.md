# openocd-flash-scripts

This repository contains a collection of scripts to flash firmware to the [Screamer PCIe Squirrel](https://docs.lambdaconcept.com/screamer/index.html) using OpenOCD.

## Usage

To flash the firmware, you need to have OpenOCD installed.

**Build on Linux**

```bash
# Clone the repository
git clone https://github.com/ntfreak/openocd.git
cd openocd

# Bootstrap the build system
./bootstrap

# Configure the build
# At the point of writing, this flag had to be passed to successfully build OpenOCD
./configure --disable-linuxgpiod

# Build
make
sudo make install
```
Navigate to the directory containing these scripts and execute one of the following commands:

**Dump firmware**

```bash
openocd -f dump.cfg
```

**Flash firmware**
Make sure you called your .bin file `firmware.bin`

```bash
openocd -f flash.cfg
```

**Verify firmware**

```bash
openocd -f verify.cfg
```
