# OptiminerZ/Zero for Fuji and AMD RX Series with 4GB RAM ONLY.
AMD 8GB cards and NVIDIA use OptiminerEquihash

!!!TRY THE SMOS INSTALL SCRIPT!!!

GPU miner for Zero.

[Download Linux 4GB GPU
64bit](https://github.com/easymine-rocks/OptiminerZero/raw/master/optiminer-zero-1.1.0.tar.gz)

[Download Windows 4GB GPU
64bit](https://github.com/easymine-rocks/OptiminerZero/raw/master/optiminer-zero-1.1.0.zip)

**Important: There are different versions for GPUs with 4GB and 8GB of RAM! If you have a card with
only 4GB download the other version (1.1.0). 4GB is for AMD only!**

<!--
### Recommended Drivers

#### Linux
- fgrlx 15.30.3 for all GCN 1st-3rd gen cards
- amdgpu-pro 16.40.5 for GCN 4th gen cards (RX4\*0)

#### Windows
- Full speed can only be achieved under Catalyst 15.12 drivers! See
  [below](#installing-catalyst-1512-on-windows) for how to install the older
  driver version.
- RX4\*0 cards are not supported by Catalyst 15.12, **I strongly recommend
  to use linux for mining on them!**
-->

### Features

Supports:
- Windows and Linux 64bit only.
- AMD GCN cards and NVIDIA.

Expected speed (stock card):
- Fiji (4GB):  7.5 S/s
- RX 290x (4GB): 5.5 S/s

The miner contains a 2.5% fee for supporting the developer. All shown hash rates 
are net rate, i.e., with fee deducted. What you see is what YOU get!

## Usage:
Run from the archive root directory:
```
$ ./optiminer-zero -s zstratum+tls://zero.easymine.rocks:3000 -u t1xxWALLETADDRESSxx.$rigName -p x
```
$ ./optiminer-zero -s zero.easymine.rocks:2000 -u t1xxWALLETADDRESSxx.$rigName -p x

For a list of all options run with `-h`:
```
$ ./optiminer-zero -h
```

## Troubleshooting

### `GLIBCXX_3.4.20' not found on Ubuntu 14.04
Install the required libstc++:
```shell
sudo add-apt-repository ppa:ubuntu-toolchain-r/test 
sudo apt-get update
sudo apt-get install libstdc++6
```

### Failed to read bin/base.bin
You need to run the miner from the directroy where optiminer-zcash is in
otherwise it will not find the opencl kernel.

### libOpenCL.so.1 cannot open object
There is a problem with your OpenCL installation. Make sure that there is a
symlink /usr/lib/libOpenCL.so.1 that points to the OpenCL library on your
system.

### [error] OpenCL error: cl::Context::Context() (CL_DEVICE_NOT_FOUND)
Either you have specified a wrong device / platform combination or there is
a problem with your OpenCL setup.

By default platform id 0 is used. You can specify a different platform by
adding '-c N' to the command line where N is a small number (try 0,1,2).

Restarting X might help to re-initialize the graphic driver under Linux.

### Internal error: Link failed
This can happen if you use an unsupported version of the graphic driver.
Try updating to the newest driver or use `--force-generic-kernel` to get a
slower implementation that also runs on older drivers.

### Installing catalyst 15.12 on Windows
- Download and run the [AMD driver
  cleanup](http://support.amd.com/en-us/kb-articles/Pages/AMD-Clean-Uninstall-Utility.aspx)
- Download and install "Download Windows 10 64-bit (Desktop)" from
  [here](http://www.guru3d.com/files-details/amd-radeon-software-crimson-15-12-driver-download.html).
  You need to scroll down to find the download links.
- Reboot. 

## Changelog
- [1.0.0] Initial release.
- [1.1.0] Special version for 4GB cards (slower).
- [1.2.0] Add support for NVIDIA cards.
