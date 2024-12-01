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


## No 2 fairy
1. Awalnya HIA dan fairy saling bisa ping
![image](https://github.com/user-attachments/assets/91874200-c9d1-445f-80a1-7d3b7da871f6)
![image](https://github.com/user-attachments/assets/8bb6544e-8673-421c-a819-59a1b08a6f58)
2. Jalankan command iptables -L INPUT -n --line-numbers
![image](https://github.com/user-attachments/assets/866c80ad-2533-4b32-a3a2-b297be51e210)
3. Jalankan command iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
![image](https://github.com/user-attachments/assets/bed08d40-244b-4136-9a39-1e67b18dad05)
4. Fairy bisa ping HIA tetapi HIA tidak bisa ping fairy
![image](https://github.com/user-attachments/assets/924c108f-bee7-4794-9a43-bbb0dbcc025e)
![image](https://github.com/user-attachments/assets/de5769b5-b8cb-4323-87f0-c7dd976c5ef2)

## No 3 HDD







