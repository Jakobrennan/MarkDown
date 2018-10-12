# Notes from Cisco Network Essentials by Try McMillan

### Describing a network
when computers were first created they were not connected, you had to transfer information between computers using a flobby disk.
This form of communication was known as `sneakernet`.
there are a few key components to a network today, usually a netowork would consist of the following:
`routers`
`computers`
`switches`

#### switches
switches come in 2 variaties:
`layer 2` switches connect computers to devices that are in the same network.
`layer 3` switches are capable of doing the same as a `layer 2` switch and also capable of acting like a router.

### Benefits of networks
there is a long list of benefits having a globally shared network, we are capable of sharing documents, files, folders, printers, computers, etc.
some key benefits include:

##### resource sharing
resource sharing is massive in the workplace, and is just as beneficial at home. In the early days there were `dumb terminals` and `mainframe computers` which were used by specialized guys in lab coats and geeks. But now people are taking advantage of this gift and 10 people are now able to work on a single docuement.

##### Reduced cost and easier installation of software
it didn't become apparent straight away, but it is possible to install software onto multiple maching over a network, which means there is a reduced cost in the way software is installed. Instead of installing an application onto multiple machines and paying for each application, you can simply put the software on a machine and let each client download the software over the network. so you would charge businesses for seating costs, not installations.
this relieves the IT staff of all the legwork involved in installing a program.

##### Improved Security
There is a lot of control over who has files on a network, and what kind of power they can have over a folder. For example, you can share the contents of a document with a number of people. Let's say 2, you could give one person 'Read' rights only, another user 'Read/Write' rights, and you can have full edit and delete rights (as you're the super-user).
This kind of control over documents with floppies wasn't possible.

##### improved commmunications
No need to keep sending information to one another through the medium of paper anymore, as people are able to talk to one another as easily as speaking to someone next to you with the use of email, instant messaging, webchats, etc. There is no need to keep multiple copies of what is sent either as emails, and messaging systems can be conifugred to keep a copy of everything that is being sent or received through it's channels.
This saves a world of paper, and makes the progression of meetings, transactinos, businesses and deals 1000x quicker than before.

##### More Workplace Flexibility
with networks comes some workplace perks, like `telecommuting` which allows someone to use another computer if their's is broken. this saves a lot of lost time in the fact that nobody has to wait around for their personal machine to be fixed. This kind of system called a `domain-based network` also allows users to work from home, or remote into a network from another location. This is becoming extremely popular and a lot of employees are 'Telecommuting' because all they need is an internet connect, and they can work as if they were just in the office.

`Peripherals` - def - a device that operates in conjuction with the computer but works outside of the computers 'box'. examples include mouse, screen, keyboard, printers, scanners and the like.

##### reduced cost of Peripherals
because any office can share devices in the office now, like printers and scanner, this means there is a lot less cost for companies to pay for such luxuries, and with less devices, there is less cost for the maintenance of these devices as well. so all around it's pretty good for the company, however it is putting people out the job as people who maintain this equipment won't be needed as much.

##### Centralized Administration
**Not possible on a peer-to-peer network**
with domain based networks, all computer adminstration is `centralized`, this means that the `LAN` administrator is responsible for the security of all the devices and the distribution of resources and the like.
All this work is done from a special kind of server called a `domain controller`. This controller is the holder of the `directory services` that is the directory that distributes all the resources available to the netwrork that is it on.

### Identifying the requirements for a network
For something to be classed as a network, there are some requirements that need to be met:
* At least 2 computers
* a shared resource
* a communications agreement (usually a protocol)
* a tranmission medium (usually some form og media)

##### At Least Two Computers
although it is obvious, transmitting information from computer A to computer B without the use of the `sneakernet` is what drove the development of networks.
a computer does not need a network to share a file with itself.

###### A resource that can be shared
anything that can be moved from one computer to another is considered a resource that can be shared. this can be anything between perihperals like printers and scanners to documents and folders.
###### A Transmission Medium
some form of communication medium is also required. A common medium is a wired connection between devices and machines, but a more and more common medium is wireless communications.

##### A Communications Agreement
when computers communciate with one another over a network, they need some sort of common ground to be able to communicate, much like two people need to be able to speak the same language to understand one another. when computers communicate over a network, the language they speak in is usually known as `protocols`, and if two machines are running different `protocols` then they will not be able to exchange information.
Example, you have 3 workstations, Wst 1 and Wst 2 both communicate in `TCP/IP` so, they are able to talk to one another without any issues, however, Wst 3 uses `IPX/SPX` which neither of the other two computers speak, so Wst 3 is not able to communicate with the other Wst's

When computers first came to be, and networks were first being established, there was no norm for what protocols machines would use, there was no standard. That has changed thanks to the internet and computer vendors, because it was a serious issue that different types of computers couldnt speak to one another, `TCP/IP` became the standard protocol that was downloaded onto all machines. But there is another piece of critical software that is needed called a `Networking Client`, that allows you to switch between different protocols, for machines that support such software.

As well as the minimum requirements for networking, networks also tend to come with fancy tools such as:
`Repeaters` - devices designed to apmlify the strength of a signal as much as possible, as well as try to keep a signal consistent. Signals that fluctuate massively tend to cause huge distruption AND corrupt data being transferred.
`Hubs` - junction boxes in networks that have no intelligence and are created to connect devices on the same physical network. `Switches` can be used in the place of `hubs`, and tend to provide a better performance as well as more functionality than a `hub`.
`Routers` - are mainly used to connect networks and allow computers located on different networks to communicate with one another. `Cisco` routers and switched are creted with intelligence because of Cisco's `Internetwork Operating System (IOS)` which is inclided in the devices as well as used to manage the devices.

'''
PROPRIETARY VS STANDARD
`Proprietary` - The definition of this term in the IT industry basically means when a process or method of something can ONLY be acheived on a certain vendors equipment
`Standard` - A standard is a process developed and agreed upon by the industry, a raw example of a 'standard' is the wall socket, every manufacturer has agreed to create a wall socket that fits the standard, because all consumers are used to that standard.
'''

### Classifying Networks by Function

#### Understanding LAN's
Differnet networking books define a `LAN` differently, Cisco define is as follows:
```
A high-speed data netowrk covering a small geographical area. `LAN's` coverage is within a physcial laoction, this could be the floor of a building, an entire buidling, or even a a small complex of buildings. 
```

The vast majority of netowork technologies will the an `Ethernet` cable, however, there are other such technologies such as `Tokein rings`. However, `Ethernet` is the 'de facto'

```
Different between `Official Standard` and `de facto`
`Official standard` - this is something that is adopted by a body formed to create standards. Such bodies are ISO (Institute of Standardization) and IEEE (Institute of Electrical and Electronics Engineering).
`de facto` - this is a process that is implemented by people over a period of time. 
```

`Ethernet Netoworks` are typically built, owned and managed by an organization. It is impractival for an organization to have an `Ethernet Network` spread over to cities, for a number of reasons.
in a `LAN` network, the computers have a high speed connection, `high-speed` is obviously a relative term, it used to indivate a connection speed of at least `10Mbps`, but nowheredays, it's closer to something like 	`100Mbps` or even `1,000Mbps`. If a complex of buildings are connected with an `Ethernet Network` and have a high speed connection, they would fit the definition of `LAN Netowrk`.

#### Understanding WAN's
a WAN is a group of LAN's connected using WAN technologies. WAN do NOT use `ethernet` to connect their LAN networks, instead they use:
	- Frame Relays
	- Intergrated Services Digital Network (ISDN)
	- point-to-point protocol (PPP)
These technologies are often used when a company decide to create their WAN by `leasing` a WAN connection from a `telecommunications company`. This is different to putting your WAN on the `internet`, which uses different technologies. Usually when you lease a WAN connection from telecommunications companies, you have the benefit of having a dedicated network, where the traffic is usually only populated by your business, and only your company and the WAN leaser can access it.

The other option is the put your network onto the `internet`, this means you will have to create a `Virtual Private Network (VPN)`. This encrypts all the data that is passed on the network so that if anybody was to intercept the data, they wouldn't be able to make use of the information they have required.

### Network Architectures

#### Peer-to-Peer Networks
`peer-to-peer` netowkrs are also known as `workgroups`. They have an interesting set up and were one of the first WAN's to be introduced. The basic premis of a `peer-to-peer` is that each computer on a network is connected to each other, and that each computer can share resources with the other computers. The catch is that the each computer is in charge of their own security, and the configuration of the computer has to be set up on each computer.
If you take a network of 4 computers for example, 4 users set up on each of the 4 computers would mean that 16 accounts will have to be created and set up. This includes the passwords, the usernames, configurations, etc. The jobs will become tedious and long the more cimputers that are connected to the network.
This can be seen as an issue, but when 10 more computers are connected in this format, 2 big problems occur:
The first is the network speed. 
When computers in this form of communication contact one another, it's the same as calling for a person in a crowded room. If a computer is contacting user 'joe', then the sending computer will have to find who 'joe' is, and once 'joe' responds, only then can the sender deliver their message. 

The second issue is a little bit bigger, and that's dependant on the client operating system (meaning the operating system that is on the client's server). Most Operating System's will only support 10 concurrent connections between computers on a `workgroup` achitecture. So if 1 computer has a popular file on it, and 10 computers are accessing it simultaneously, then the 11th computer won't be able to view or access the file until their is a spot available.

However, there are many benefits to a `peer-to-peer` network. Some of those include the fact that a `workgroup` network is cheap and easy to set up. Many SOHO (small office & home office) networks will have a `peer-to-peer` network because they don't demand a high amount of traffic and can easily be set up as they don't require a server of any kind.
However this means they aren't scalable, in that they cannot have many computers added to the network.
In short the advantages:
	- Low Cost
	- Easy to set up
	- No server required
Disadvantages:
	- No centralized control of security
	- Administrative burden of maintaining accounts on all computers.
	- No scalability


