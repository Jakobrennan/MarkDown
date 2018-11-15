# linux command line and shell scripting 

[Basics](#Basics)

- [Linux Kernel](#Linux Kernel)
- [System Memory Management](#System Memory Management)
- [Software Program Management](#Software Program Management)
- [Hardware Management](#Hardware Management)

## Basics

linux is broken down into 4 main parts:

- Linux Kernel
- GNU Utilities
- Graphical Desktop Environment
- Application Software

here's a basic diagram of how they fit together

       ++----------------------------------------------------------------------------+
       |                           Application Software                              |
       +-----------------------------------------------------------------------------+
       +-----------------------------------------------------------------------------+
       |                                                                             |
       |                                  +------------------------------------------+
       |            Window                |
       |          Management              |  +---------------------------------------+
       |           Software               |  |                                       |
       |                                  |  |               GNU                     |
       |                                  |  |              System                   |
       |                                  |  |             Utilities                 |
       |                                  |  |                                       |
       +----------------------------------+  +---------------------------------------+
       +-----------------------------------------------------------------------------+
       |                            Linux Kernel                                     |
       +-----------------------------------------------------------------------------+
       +-----------------------------------------------------------------------------+
       |                          Computer Hardware                                  |
       +-----------------------------------------------------------------------------+

#### Linux Kernel

The *core* of the linux opertating system is the Linus Kernel, which is a special piece of software that allocates hardware when necessary and executes software when required.

_Linus Torvald_ was the student (at the time) who developed the linux kernel, with the intention of replicating the popular *Unix Oprating System*, *Linus* made the *Linux Kernel* _opensource_ which allowed students and proffessionals alike to develop and edit it.
_Linus_ would only implement changes he approved of and as of today he still looks over the implementations of new code with a team of developers.

The *kernel* is responsible for:

- System Memory Management
- Software Program Management
- Hardware Management
- FileStystem Management

##### System Memory Management

the *Primiary Function* of the OS *Kernel* is the _memory management_. The Kernel can manage both *Physical memory* and *Virtual Memory*.
The *Kernel* interchanges data on the hard disk known as *swap space*, which allows the machine to think there is more memeory that there actually is.

    _Diagram of Linux Memory Map_
                                                      Physical Memeory
                                                         +---------+
                     Virtual Memory                      +---------+
                     +-----------+\      +-------+      /+---------+
                     +-----------+ \     |       |     / +---------+
                     +-----------+  \    |       |    /
                     +-----------+   \   |       |   /
                     +-----------+    \  |       |  /
                     +-----------+     \ |       | /
                     +-----------+      X|       |X
                     +-----------+     / |       | \
                     +-----------+    /  |       |  \
                     +-----------+   /   |       |   \    Swap Space
                     +-----------+  /    |       |    \  +-----------+
                     +-----------+ /     +-------+     \ |           |
                     +-----------+/      The Kernel     \| +-------+ |
                                                         | +-------+ |
                                                         |\+-------+ |
                                                         | +-------+ |
                                                         | +-------+ |
                                                         | +-------+ |
                                                         | +-------+ |
                                                         |           |
                                                         +-----------+
                                               
Memory locations are called *pages*
*Kernel* locates *pages* in either swap space or physical space
*Kernel* maintains a table of *memory pages* which label which page are in physical and which are in swap space

_Swapping out_ - when a *page* in the physical memory hasn't been used for a period of time, it is swapped and put into *swap space*

When a program wants to access a *Page* that has been _swapped out_, then the *Kernel* must make room on the physical memory, by swapping out *pages* that haven't been used for a while. This process can slow down the machine, but the process lasts for as long as linux is running.

##### Software Program Management

The linux os calls a running programm a *process*. 
A *Process* can be either in the _foreground_ or the _background_. the *Kernel* decides how the _Linux System_ manages the *process'*

Initially, the *Kernel* creates an *init process* which is opened in the _swap space_.
All following *process'* are opened in the _swap space_ but are procivded a unique area by the *Kernel*.

                                     Swap Space      
       +---------------------------------------------------------------------+
       |               +--------+                                            |
       |               |        |+-----------+ +-----------+                 |
       |               |        ||           | |           |                 |
       |               |        ||           | |           |                 |
       |               |        ||  Process  | |  Process  |                 |
       |               |        ||           | |           |                 |
       |               |        ||           | |           |                 |
       |               |  init  ||      ID:1 | |      ID:3 |                 |
       |               |process |+-----------+ +-----------+                 |
       |               |        |                                            |
       |               |        |+-----------+ +-----------+                 |
       |               |        ||           | |           |                 |
       |               |        ||           | |           |                 |
       |               |        ||  Process  | |  Process  |                 |
       |               |        ||           | |           |                 |
       |               |        ||           | |           |                 |
       |               |        ||      ID:2 | |      ID:4 |                 |
       |               |        |+-----------+ +-----------+                 |
       |               +--------+                                            |
       |                                                                     |
       +---------------------------------------------------------------------+
_Diagram of process map_

There exists an _init_ table that holds the process started automatically at bootup. The paths are:

| Distro | Path |
|---|---|
| Ubuntu | /etc/init.d |
| others | /etc/inittabs |

Distro's like _ubuntu_ have scripts that start and stop at boot time and are started based of their *run level*.
They can be found at _/etc/rcX.d folders_ (where X is the *run level*)

*Run Level's* are used to derect the _init process_ to run only certain types of *process'* defined by their *run level*.

_Run Level 1_
also known as *single-user mode*, this level allows very basic system requirements for the system and allows a single terminal to run. This is usually accessed by the _administrator_ and can be used to log into systems and manipulate _data_.

_Run Level 3_
This is the standard *run level*. This level runs most application software, and where the likes of _network support software_ is started.

_Run Level 5_
This level is where the graphical X window is started and allows the ability to log in with graphical desktop windows.


The linux system controlls the overall system functionality by controlling the _init run level_.

##### Hardware Management

the *Kernel* also manages hardware, typically any device that the _Linux system_ must comminicate with, needs drivers inserted into the kernel code. this allows the *kernel* to pass data between applications and the components.
The 2 methods of insterting device drivers are:

- Drivers compiled in the kernel

- Driver Modules being added to the kernel

The old way of inserting driver code into the *kernel* would be to recompile the *Kernel* everytime you acquired more hardware. This became extremely inefficient, quickly.

The use of *Kernel Modules* came about to fix the issue of recompliling the *Kernel* constanstly. Inserting _modules_ allowed you to insert driver code into the *kernel* whilst it was running, which became even more helpful the mor linux expanded their hardware.

the _Linux System_ places hardware devices in special files knows as *device files* on the system, and are split into 3 catagories:

- Character

- Block

- Network

_Character device files_ - are devices that can only handle 1 bit at a time, such as modems and terminals.

_Block device files_ - thes files are for devices that can handle large blocks of data at a time, like cd drives.

_network device files_ - These files are for devices that use packets to send and receive data, like network cards or loopback devices.

<u>Nodes</u>
_nodes_ are special files on the system that allow the communication betweent he *Kernel* and the devices on the machine.
a _Unique number pair_ identifies the device with the *Linux Kernel*.
the number pairs are devided into _major_ and _minor_ device numbers:

_Major_ - this is when a group of similar devices have their _nodes_ given the same _Major device number_ so they become a group.

_Minor_ - These are allocated to specifiy the individual device for the *Kernel* to be able to access it.

##### Filesystem Management

Unlike other operating systems, _Linux_ has the cabalility to be able to _read_ and _write_ to different _filesystems_. Although Linuz has a number of _filesystems_ of it's own already, it can use _filesystems_ from other Opersating systems, line windows.
For this to work the *Kernel* must be compiled with the standard filesystems that linux needs to use to read and write.

here is a table to show you what's included:

| Filesystem | Description                                                        |
|------------|--------------------------------------------------------------------|
| ext        | Linux Extended filesystem - the original Linux Filesystem          |
| ext2       | Second extended filesystem, provided advanced features over ext    |
| ext3       | Third extended filesystem, supports journaling                     |
| ext4       | Fourth extended filesystem, supports advanced journaling           |
| hpfs       | OS/2 high-performance filesystem                                   |
| jfs        | IBM's journaling filesystem                                        |
| iso9660    | ISO 9660 filesystem (CD-ROMS's)                                    |
| minx       | MINIX filesystem                                                   |
| msdos      | Microsoft FAT16                                                    | 
| ncp        | Netware filesystem                                                 |
| nfs        | Network filesystem                                                 |
| ntfs       | Support for Microsoft NT filesystem                                |
| proc       | Access to system information                                       |
| ReiserFS   | Advanced linux filesystem for better performance and disk recovery |
| smb        | Samba SMB filesystem for network access                            | 
| sysv       | Older unix filesystem                                              |
| ufs        | BSD filesystem                                                     |
| umsdos     | Unix-like filesystem that resides on top of msdos                  |
| vfat       | windows 95 filesystem (FAT 32)                                     |
| XFS        | High-performance 64-bit journaling filesystem                      |


Any hard-drive that a Linuz system has to access must be formatted using one of the filesystems above

the *Linux Kernel* interfaces with each filesystem using the _Virtual File System (VFS)_.
This provides the inferface for the *kernel* to communicate with any type of filesystem. 
VFS caches information in memory as each filesystem is mounted and used.

#### The GNU Utilities


