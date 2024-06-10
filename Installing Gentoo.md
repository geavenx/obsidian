
All information is on https://wiki.gentoo.org/wiki/Handbook:AMD64. This note is a step-by-step guide for future personal orientation

# Hardware requirements

| Name     | Minimum requirement |
| -------- | ------------------- |
| **Disk** | 8GB + swap          |
| **Swap** | see swap            |
| **CPU**  | Any x86-64          |
| **RAM**  | 2GB                 |
### Swap space


# Image

Download the minimal installation CD from the [official Gentoo downloads page](https://www.gentoo.org/downloads/)
### Writing a bootable USB

#### Using dd
Execute the command *lsblk* to find your USB storage location, then run:
- `root # dd if=<your-downloaded-minimal-iso> of=/dev/<your-USB-here> bs=4096 status=progress && sync`

	***if***=input file; **of***=output file.

Now boot your computer into this newly created USB live disk.

# First steps

#### Start ssh daemon
If you want to setup your system from another computer via SSH, you need to fire up the SSH daemon, to to that execute the command:
-  `root # rc-service sshd start`

#### Network
It is very likely that this is done automatically, but if is not, go through this section. Also for additional troubleshooting and knowledge you should check the official documentation on the topic: [Gentoo wiki networking section](https://wiki.gentoo.org/wiki/Handbook:AMD64/Installation/Networking).

This guide covers only cabled connection, for configuring WiFi, check the documentation linked above.

If it is not running, you can try running *dhcpd* on your network interface. First, to check your network interfaces run:
- `root # ip link`

You should see a list of network interfaces, that starts with the index of each one, followed by the name, something like this:
```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
4: enp1s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP mode DEFAULT group default qlen 1000
    link/ether e8:40:f2:ac:25:7a brd ff:ff:ff:ff:ff:ff
```
***lo*** stands for loopback, that is not what you want. You are looking for your actual network device, in the case *enp1s0*:
- `root # dhcpd enp1s0`

**Testing connection**

To test basic internet connectivity, use the *ping* command:
- `root # ping -c 4 8.8.8.8`

For DNS resolutions:
- `root # ping -c 4 google.com`

# Disk partitioning
