# Modul 5 Jarkom

## **Topologi**

![image.png](image.png)

**NewEridu**

```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
  address 10.73.0.1
  netmask 255.255.255.252

auto eth2
iface eth2 inet static
  address 10.73.0.5
  netmask 255.255.255.252

#A6
post-up route add -net 10.73.2.0 netmask 255.255.255.248 gw 10.73.0.2

#A3
post-up route add -net 10.73.0.8 netmask 255.255.255.248 gw 10.73.06

#A8
post-up route add -net 10.73.2.64 netmask 255.255.255.192 gw 10.73.0.2

#A7
post-up route add -net 10.73.2.8 netmask 255.255.255.248 gw 10.73.0.2

#A4
post-up route add -net 10.73.0.128 netmask 255.255.255.128 gw 10.73.0.6

#A5
post-up route add -net 10.73.1.0 netmask 255.255.255.0 gw 10.73.0.6

#A9
post-up route add -net 10.73.2.128 netmask 255.255.255.252 gw 10.73.0.2

```

**SixStreet (DHCP Relay)**

```
auto eth0
iface eth0 inet static
  address 10.73.0.2
  netmask 255.255.255.252
  gateway 10.73.0.1

auto eth1
iface eth1 inet static
  address 10.73.2.1
  netmask 255.255.255.248

auto eth2
iface eth2 inet static
  address 10.73.2.9
  netmask 255.255.255.248

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A8
post-up route add -net 10.73.2.64 netmask 255.255.255.192 gw 10.73.2.3

#A9
post-up route add -net 10.73.2.128 netmask 255.255.255.252 gw 10.73.2.2

#A4
post-up route add -net 10.73.0.128 netmask 255.255.255.128 gw 10.73.0.1

```

**HDD (DNS)**

```
auto eth0
iface eth0 inet static
  address 10.73.2.10
  netmask 255.255.255.248
  gateway 10.73.2.9

up echo nameserver 192.168.122.1 > /etc/resolv.conf

```

**Fairy (DHCP)**

```
auto eth0
iface eth0 inet static
  address 10.73.2.11
  netmask 255.255.255.248
  gateway 10.73.2.9

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A8
post-up route add -net 10.73.2.16 netmask 255.255.255.192 gw 10.73.2.9

#A4
post-up route add -net 10.73.0.128 netmask 255.255.255.128 gw 10.73.2.9

```

**OuterRing (DHCP Relay)**

```
auto eth0
iface eth0 inet static
  address 10.73.2.3
  netmask 255.255.255.248
  gateway 10.73.2.1

auto eth1
iface eth1 inet static
  address 10.73.2.65
  netmask 255.255.255.192

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A9
post-up route add -net 10.73.2.128 netmask 255.255.255.252 gw 10.73.2.2

#A1
post-up route add -net 10.73.0.0 netmask 255.255.255.252 gw 10.73.2.1

#A7
post-up route add -net 10.73.2.8 netmask 255.255.255.248 gw 10.73.2.1

```

**Burnice (Client)**

```
auto eth0
iface eth0 inet dhcp

#Hollowzero
post-up route add -net 10.73.2.128 netmask 255.255.255.252 gw 10.73.2.65

#A1
post-up route add -net 10.73.0.0 netmask 255.255.255.252 gw 10.73.2.65

```

**Caesar (Client)**

```
auto eth0
iface eth0 inet dhcp

#Hollowzero
post-up route add -net 10.73.2.128 netmask 255.255.255.252 gw 10.73.2.65

#A1
post-up route add -net 10.73.0.0 netmask 255.255.255.252 gw 10.73.2.65

```

**LuminaSquare (DCHP Relay)**

```
auto eth0
iface eth0 inet static
  address 10.73.0.6
  netmask 255.255.255.252
  gateway 10.73.0.5

auto eth1
iface eth1 inet static
  address 10.73.0.9
  netmask 255.255.255.248

auto eth2
iface eth2 inet static
  address 10.73.1.1
  netmask 255.255.255.0

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A1
post-up route add -net 10.73.0.0 netmask 255.255.255.252 gw 10.73.0.5

#A4
post-up route add -net 10.73.0.128 netmask 255.255.255.128 gw 10.73.0.11

#A7
post-up route add -net 10.73.2.8 netmask 255.255.255.248 gw 10.73.0.5

```

**Jane (Client)**

```
auto eth0
iface eth0 inet dhcp

```

**Policeboo (Client)**

```
auto eth0
iface eth0 inet dhcp

```

**HIA (Web Server)**

```
auto eth0
iface eth0 inet static
  address 10.73.0.10
  netmask 255.255.255.248
  gateway 10.73.0.9

up echo nameserver 192.168.122.1 > /etc/resolv.conf

```

**HollowZero (Web Server)**

```
auto eth0
iface eth0 inet static
  address 10.73.2.130
  netmask 255.255.255.252
  gateway 10.73.2.129

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A1
post-up route add -net 10.73.0.0 netmask 255.255.255.252 gw 10.73.2.129

```

**BalletTwins (DHCP Relay)**

```
auto eth0
iface eth0 inet static
  address 10.73.0.11
  netmask 255.255.255.248
  gateway 10.73.0.9

auto eth1
iface eth1 inet static
  address 10.73.0.129
  netmask 255.255.255.128

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A2
post-up route add -net 10.73.0.4 netmask 255.255.255.252 gw 10.73.0.9

#A1
post-up route add -net 10.73.0.0 netmask 255.255.255.252 gw 10.73.0.9

#A7
post-up  route add -net 10.73.2.8 netmask 255.255.255.248 gw 10.73.0.9

```

**Ellen (Client)**

```
auto eth0
iface eth0 inet dhcp
```

**Lycaon (Client)**

```
auto eth0
iface eth0 inet dhcp
```

**ScootOutpost**

```jsx
auto eth0
iface eth0 inet static
  address 10.73.2.2
  netmask 255.255.255.248
  gateway 10.73.2.1

auto eth1
iface eth1 inet static
  address 10.73.2.129
  netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A2
post-up route add -net 10.73.0.4 netmask 255.255.255.252 gw 10.73.2.1

#A8
post-up route add -net 10.73.2.16 netmask 255.255.255.192 gw 10.73.2.3

#A1
post-up  route add -net 10.73.0.0 netmask 255.255.255.252 gw 10.73.2.1
```
