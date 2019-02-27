# mbed-hera

## Getting started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

* Development card's drivers (see your manufacturer).

* [OpenOCD](http://gnutoolchains.com/arm-eabi/openocd/)

* [GNU Tools Arm Embedded](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads)

* [Mbed CLI](https://github.com/ARMmbed/mbed-cli#installing-mbed-cli).

### Get mbed-os files

From the command-line, update the mbed-os libraries:

```
mbed update master
```

### Now compile

Invoke `mbed compile`, and specify the name of your platform and your favorite toolchain (`GCC_ARM`, `ARM`, `IAR`). For example:

```
mbed compile --profile=debug -t GCC_ARM -m NUCLEO_F103RB
```

Your PC may take a few minutes to compile your code. At the end, you see a similar result:

```
[snip]
+----------------------------+-------+-------+------+
| Module             |     .text |    .data |     .bss |
|--------------------|-----------|----------|----------|
| [fill]             |    98(+0) |    0(+0) | 2211(+0) |
| [lib]/c.a          | 27835(+0) | 2472(+0) |   89(+0) |
| [lib]/gcc.a        |  3168(+0) |    0(+0) |    0(+0) |
| [lib]/misc         |   248(+0) |    8(+0) |   28(+0) |
| [lib]/nosys.a      |    32(+0) |    0(+0) |    0(+0) |
| main.o             |   924(+0) |    0(+0) |   12(+0) |
| mbed-os/components |   134(+0) |    0(+0) |    0(+0) |
| mbed-os/drivers    |    56(+0) |    0(+0) |    0(+0) |
| mbed-os/features   |    42(+0) |    0(+0) |  184(+0) |
| mbed-os/hal        |  2087(+0) |    8(+0) |  152(+0) |
| mbed-os/platform   |  3633(+0) |  260(+0) |  209(+0) |
| mbed-os/rtos       |  9370(+0) |  168(+0) | 6053(+0) |
| mbed-os/targets    |  9536(+0) |   12(+0) |  382(+0) |
| Subtotals          | 57163(+0) | 2928(+0) | 9320(+0) |
Total Static RAM memory (data + bss): 12248(+0) bytes
Total Flash memory (text + data): 60091(+0) bytes

Image: ./BUILD/K64F/GCC_ARM/mbed-os-example-blinky.bin
```

### Program your board

1. Connect your Mbed device to the computer over USB.
1. Copy the binary file to the Mbed device.
1. Press the reset button to start the program.

### Output

To view the serial output you can use any terminal client of your choosing such as [PuTTY](http://www.putty.org/) or [CoolTerm](http://freeware.the-meiers.org/). Unless otherwise specified, printf defaults to a baud rate of 9600 on Mbed OS.
