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

## MISI 1

### NO 4
DHCP Relay (OuterRing, SixStreet, LuminaSquare, BalletTwins):
```
apt-get update
apt-get install isc-dhcp-relay -y
service isc-dhcp-relay start

echo 'SERVERS="10.73.2.11"
INTERFACES="eth0 eth1 eth2 eth3"
OPTIONS=' > /etc/default/isc-dhcp-relay

service isc-dhcp-relay restart
```

DHCP Server (Fairy):
```
apt-get update
apt-get install isc-dhcp-server -y
service isc-dhcp-server start

echo 'INTERFACESv4="eth0"' > /etc/default/isc-dhcp-server

# A4
echo 'subnet 10.73.0.128 netmask 255.255.255.128 {
        range 10.73.0.129 10.73.0.254;
        option routers 10.73.0.129;
        option broadcast-address 10.73.0.255;
        option domain-name-servers 10.73.2.10; #IP DNS Server
}
# A5
subnet 10.73.1.0 netmask 255.255.255.0 {
        range 10.73.1.1 10.66.1.254;
        option routers 10.73.1.1;
        option broadcast-address 10.73.1.255;
        option domain-name-servers 10.73.2.10; #IP DNS Server
}
# A8
subnet 10.73.2.64 netmask 255.255.255.192 {
        range 10.73.2.65 10.73.2.126;
        option routers 10.73.2.65;
        option broadcast-address 10.73.2.127;
        option domain-name-servers 10.73.2.10; #IP DNS Server
}
#A7
subnet 10.73.2.8 netmask 255.255.255.248 {}'>/etc/dhcp/dhcpd.conf
```

DNS Server HDD:
```
apt-get update
apt-get install bind9 -y

echo 'options {
        directory "/var/cache/bind";

        forwarders {
            192.168.122.1;
        };

        allow-query{any;};

        auth-nxdomain no;    # conform to RFC1035
        listen-on-v6 { any; };
};' > /etc/bind/named.conf.options

service bind9 restart
```

Webserver:
```
apt-get update
apt-get install apache2 -y

HOST=$(hostname)
echo "Welcome to $HOST" > /var/www/html/index.html

service apache2 restart
```

## MISI 2

### NO 1
1. Jalankan script berikut pada NewEridu
   ```
   ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')
   iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
   ```
2. Ping google.com untuk mengecek
   ![image](https://github.com/user-attachments/assets/47bdab65-f0b1-418c-bb48-2caf45012d70)


### NO 2
1. Awalnya HIA dan fairy saling bisa ping
   ![image](https://github.com/user-attachments/assets/91874200-c9d1-445f-80a1-7d3b7da871f6)
   ![image](https://github.com/user-attachments/assets/8bb6544e-8673-421c-a819-59a1b08a6f58)
2. Jalankan command berikut agar tidak ada perangkat yang bisa ping fairy
   ```
   iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
   ```
   ![image](https://github.com/user-attachments/assets/bed08d40-244b-4136-9a39-1e67b18dad05)
4. Fairy bisa ping HIA tetapi HIA tidak bisa ping fairy
   ![image](https://github.com/user-attachments/assets/924c108f-bee7-4794-9a43-bbb0dbcc025e)
   ![image](https://github.com/user-attachments/assets/de5769b5-b8cb-4323-87f0-c7dd976c5ef2)


### NO 3 
1. Jalankan script pada DHCP server HDD agar hanya Fairy yang dapat mengakses HDD
   ```
   iptables -A INPUT -s 10.73.2.11 -j ACCEPT
   iptables -A INPUT -j DROP
   ```
   ![image](https://github.com/user-attachments/assets/cfeefced-bcc9-4b7c-bc46-98ce1fb3cd12)
2. Fairy bisa ping HDD namun perangkat lain tidak bisa
   ![image](https://github.com/user-attachments/assets/9c8d907b-d9d6-4cb9-bbaf-bbb2b15cde0d)
   ![image](https://github.com/user-attachments/assets/6b6d31cf-0433-4b45-b8f3-df8d7ddc159c)
4. Saat ditest menggunakan nc dari fairy
   ![image](https://github.com/user-attachments/assets/ad12049b-d328-449e-b7eb-186a63e8c559)
   ![image](https://github.com/user-attachments/assets/e0443cec-b0b1-4284-ac91-bae2aeccc5be)
5. Saat ditest menggunakan nc dari ballettwins
   ![image](https://github.com/user-attachments/assets/fabdc1e2-7753-428f-8408-dc04d6c884d6)
   ![image](https://github.com/user-attachments/assets/5020c818-c48f-4b84-95c2-7f87592c310e)




   







