
# SCROD Ethernet example 


## Building

This Project is using the vhdl_build_system. It use is very simple first you have to setup your build system. You do this by using this command:

```Bash
python vhdl_build_system/vhdl_make_build_system.py

```

It has the following paramters

```Bash

usage: vhdl_make_build_system.py [-h] [--path PATH] [--ssh SSH]
                                 [--remotePath REMOTEPATH]
                                 [--protoBuild PROTOBUILD]

Make build scripts for vhdl_build_system

optional arguments:
  -h, --help            show this help message and exit
  --path PATH           Path to where the build system should be located
  --ssh SSH             ssh configuration used for running the Xilinx programs
                        remotly
  --remotePath REMOTEPATH
                        Path on the remote machine that has the Xilinx
                        programs
  --protoBuild PROTOBUILD
                        Path to the proto build files
```

if you have a local installation of xilinx tools no further parameters are requiert. If you are using the VM then you have to specify the ssh connection and the remotePath. 


once this is done you can start creating xise files by using:

```Bash
 ./make_implementation.sh scrodEthernetExample ./firmware-ethernet/ExampleProject/projectSrc/scrodEthernetExample.ucf

```

once you have done this you have a new xise file in the folder ./build/scrodEthernetExample

At the moment you need to oben the ISE GUI to build the project.