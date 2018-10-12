# Devops Automation Cookbook

#### intro : setting up a server on linux

find the information, like ip address, mac address, interface options, etc, with:

```bash
ip addr show
```

And show specific options with

```bash
ip addr show <interface>
```

Add an ip4 address to the list. You need to add the `netmask` along with it, in the format of **classless inter-domain reouting (CIDR)**.

```bash
ip addr add <IP address>/<CIDR> dev <device>
```

`example` - if you want to add a new `RFC1918`-compliant address, you'd do this:

```bash
ip addr add 10.132.1.1/24 dev eth1
```

you can easily confirm the new address with:

```bash
ip addr show eth1
```

The removal of an address is the strightforward reversal of the way you added it. Simply do the above with `del` as opposed to `add`:

```bash
ip addr del <IP address>/<CIDR> dev <device>
```

```bash
ip addr del 10.132.1.1/24 dev eth1
```



To bring an interface `down`, you use the `ip link` command, followed by the interface name and teh desired state.

```bash
ip link set eth2 down
```

and simply put the back up by:

```bash
ip link set eth2 up
```

and simply check the status of the interface with the `ip` command:

```bash
ip addr eth2
```



#### Monitoring network details with the IP command

The `ip` command can not only be used for basic interfacing commands, but it can also be used to check the `functionality` of the interfaces. The first place to look when trying to figure out the main issue of a network is within the `networking stack`.

here are the basic steps

```bash
ip -s link
```

This allows you to see the basic network statistics on all interfaces.

```bash
#Output

1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    RX: bytes  packets  errors  dropped overrun mcast   
    1120036    16054    0       0       0       0       
    TX: bytes  packets  errors  dropped carrier collsns 
    1120036    16054    0       0       0       0       
2: enp3s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc pfifo_fast state DOWN mode DEFAULT group default qlen 1000
    link/ether a4:4c:c8:10:9b:a4 brd ff:ff:ff:ff:ff:ff
    RX: bytes  packets  errors  dropped overrun mcast   
    0          0        0       0       0       0       
    TX: bytes  packets  errors  dropped carrier collsns 
    0          0        0       0       0       0       
3: wlp2s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP mode DORMANT group default qlen 1000
    link/ether ac:ed:5c:f5:7a:a8 brd ff:ff:ff:ff:ff:ff
    RX: bytes  packets  errors  dropped overrun mcast   
    900136869  689337   0       0       0       0       
    TX: bytes  packets  errors  dropped carrier collsns 
    21150253   126155   0       0       0       0  
```

here you get a list of the interface configuration options, as well as the MAC address and interface statistics.

> by default, the columns of the `ip -s link` command stand for the following:
>
> `RX/TX: bytes` - the total number of bytes sent/received by this inteface.
>
> `RX/TX: packets` - total number of network packets sent/received by this interface.
>
> `RX/TX: errors` - total number of transmission errors found on this interface.
>
> `RX/TX: Dropped` - total number of networking packets
>
> `RX: mcast` - received multicast packets
>
> `TX: collsns` - network packets collisions

with the following command, you can see the output of a single interface:

```bash
ip -s link ls <<interface>>
```

see the statistics of the `enp3s0` inteface in the `#output` above, use the following command:

```bash
ip -s link ls enp3s0
```

to see even more information, simply append another `-s` tag to the command:

```bash
ip -s -s link ls enp3s0
```



#### Monitoring connections using the `ss` command

