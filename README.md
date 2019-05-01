# Glasgow Debug Tool

**Want one? [Subscribe here](https://mailchi.mp/44980ff6f0ab/glasgow-announcements).**

**Let's chat! [Our IRC channel is #glasgow at freenode.net](https://webchat.freenode.net/?channels=glasgow).**

**Important note: if you are looking to assemble boards yourself, wait until revC1 is finalized.**

## What is Glasgow?

Glasgow is a tool for exploring digital interfaces, aimed at embedded developers, reverse engineers, digital archivists, electronics hobbyists, and everyone else who wants to communicate to a wide selection of digital devices with high reliability and minimum hassle. It can be attached to most devices without additional active or passive components, and includes extensive protection from unexpected conditions and operator error.

The Glasgow hardware can support many digital interfaces because it uses reconfigurable logic. Instead of only offering a small selection of standard hardware supported interfaces, it uses an FPGA to adapt on the fly to the task at hand without compromising on performance or reliability, even for unusual, custom or obsolete interfaces.

The Glasgow software is a set of building blocks designed to eliminate incidental complexity. Each interface is packaged into a self-contained *applet* that can be used directly from the command line, or reused as a part of a more complex system. Using Glasgow does not require any programming knowledge, although it becomes much more powerful if you know a bit of Python.

## What hardware does Glasgow use?

The Glasgow hardware evolves over time, with each major milestone called a "revision". Although all revisions are, and will always be supported with the same software, they vary significantly in their capabilities, and the chosen revision will limit the possible tasks.

Glasgow boards use a version in the `revXN` format, where `X` is a revision letter (increased on major design changes) and `N` is a stepping number (increased on any layout or component changes). For example, `revC0` is the first stepping of revision C.

### revA/revB

Revisions A and B have not been produced in significant amounts, contain major design issues, and are therefore mostly of historical interest. Nevertheless, everyone who has one of the revA/revB boards can keep using them—forever.

### revC

![Overview of the Glasgow PCB](hardware/boards/glasgow/3drender-readme.png)

Revision C is the revision being actively worked on. It provides 16 I/O pins with a maximum frequency of approx. 100 MHz\*, independent direction control and independent programmable pull-up/pull-down resistors. The I/O pins are grouped into two I/O ports that can use any voltage from 1.8 V to 5 V, sense and monitor I/O voltage of the device under test, as well as provide up to 150 mA of power. The board uses USB 2 for power, configuration, and communication, achieving up to 336 Mbps (42 MB/s) of sustained combined throughput.

<sub>\* Maximum frequency achievable in practice depends on many factors and will vary greatly with specific interface and applet design. 24 MHz non-DDR can be achieved for most interfaces with minimal effort.</sub>

## Contributors

  * [@whitequark](https://github.com/whitequark) came up with the design, coordinates the project and implements most of gateware and software;
  * [@awygle](https://github.com/awygle) designed the power/analog port circuitry and helped with layout of revB;
  * [@marcan](https://github.com/marcan) improved almost every aspect of hardware for revC;
  * [@esden](https://github.com/esden) is handling batch manufacturing;
  * [@smunaut](https://github.com/smunaut) provided advice crucial for stability and performance of USB communication;
  * ... and many [other people](https://github.com/GlasgowEmbedded/Glasgow/graphs/contributors).

## License

_Glasgow_ is distributed under the terms of both 0-clause BSD license as well as Apache 2.0 license.

See [LICENSE-0BSD](LICENSE-0BSD.txt) and [LICENSE-Apache-2.0.txt](LICENSE-Apache-2.0.txt) for details.
