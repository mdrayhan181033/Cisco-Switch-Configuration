Narayangong-SW# show running-config

!Command: show running-config
!Running configuration last done at: Sun Aug 31 05:31:30 2025
!Time: Mon Sep  1 14:50:40 2025

version 10.3(1) Bios:version 05.47 [last: 05.28]
hostname Narayangong-SW
vdc Narayangong-SW id 1
  limit-resource vlan minimum 16 maximum 4094
  limit-resource vrf minimum 2 maximum 4096
  limit-resource port-channel minimum 0 maximum 511
  limit-resource m4route-mem minimum 58 maximum 58
  limit-resource m6route-mem minimum 8 maximum 8

feature telnet
nv overlay evpn
feature ospf
feature bgp
feature pim
feature msdp
feature fabric forwarding
feature interface-vlan
feature vn-segment-vlan-based
feature lacp
feature lldp
feature bfd
feature nv overlay

username admin password 5 $5$CNY6VZiZ$6fy/d2H4RrpgaFTjBKmy/PvBubxmjUJoy05dNl4rIzA  role network-admin
ip domain-lookup
copp profile strict
snmp-server user admin network-admin auth md5 0x4bde6c35b272f25b65d133274b361d0e priv des 0x4bde6c35b272f25b65d133274b361d0e localizedkey
rmon event 1 description FATAL(1) owner PMON@FATAL
rmon event 2 description CRITICAL(2) owner PMON@CRITICAL
rmon event 3 description ERROR(3) owner PMON@ERROR
rmon event 4 description WARNING(4) owner PMON@WARNING
rmon event 5 description INFORMATION(5) owner PMON@INFO
snmp-server community Speed group network-operator

ip route 0.0.0.0/0 172.16.100.1
vlan 1-3967
vlan 805
  vn-segment 15805
vlan 806
  vn-segment 15806
vlan 807
  vn-segment 15807
vlan 808
  vn-segment 15808
vlan 1096
  vn-segment 151096
vlan 1142
  vn-segment 151142
vlan 1222
  vn-segment 151222
vlan 1337
  vn-segment 151337
vlan 1340
  vn-segment 151340
vlan 1342
  vn-segment 151342
vlan 1392
  vn-segment 151392
vlan 1398
  vn-segment 151398
vlan 1440
  vn-segment 151440
vlan 1491
  vn-segment 151491
vlan 1640
  vn-segment 151640
vlan 1772
  vn-segment 151772
vlan 1775
  vn-segment 151775
vlan 1840
  vn-segment 151840
vlan 1842
  vn-segment 151842
vlan 1854
  vn-segment 151854
vlan 2142
  vn-segment 152142
vlan 2340
  vn-segment 152340
vlan 2343
  vn-segment 152343
vlan 2372
  vn-segment 152372
vlan 2375
  vn-segment 152375
vlan 2392
  vn-segment 152392
vlan 2440
  vn-segment 152440
vlan 2633
  vn-segment 152633
vlan 2640
  vn-segment 152640
vlan 2642
  vn-segment 152642
vlan 2661
  vn-segment 152661
vlan 2751
  vn-segment 152751
vlan 2759
  vn-segment 152759
vlan 2774
  vn-segment 152774
vlan 2867
  vn-segment 152867
vlan 3142
  vn-segment 153142
vlan 3149
  vn-segment 153149
vlan 3340
  vn-segment 153340
vlan 3342
  vn-segment 153342
vlan 3372
  vn-segment 153372
vlan 3392
  vn-segment 153392
vlan 3440
  vn-segment 153440

vrf context management

interface Vlan1

interface Vlan3100
  no shutdown
  ip address 172.16.100.246/24

interface nve1
  no shutdown
  host-reachability protocol bgp
  member vni 15805
    suppress-arp
    ingress-replication protocol bgp
  member vni 15806
    suppress-arp
    ingress-replication protocol bgp
  member vni 15807
    suppress-arp
    ingress-replication protocol bgp
  member vni 15808
    suppress-arp
    ingress-replication protocol bgp
  member vni 151096
    suppress-arp
    ingress-replication protocol bgp
  member vni 151142
    suppress-arp
    ingress-replication protocol bgp
  member vni 151222
    suppress-arp
    ingress-replication protocol bgp
  member vni 151337
    suppress-arp
    ingress-replication protocol bgp
  member vni 151340
    suppress-arp
    ingress-replication protocol bgp
  member vni 151342
    suppress-arp
    ingress-replication protocol bgp
  member vni 151392
    suppress-arp
    ingress-replication protocol bgp
  member vni 151398
    suppress-arp
    ingress-replication protocol bgp
  member vni 151440
    suppress-arp
    ingress-replication protocol bgp
  member vni 151491
    suppress-arp
    ingress-replication protocol bgp
  member vni 151640
    suppress-arp
    ingress-replication protocol bgp
  member vni 151772
    suppress-arp
    ingress-replication protocol bgp
  member vni 151775
    suppress-arp
    ingress-replication protocol bgp
  member vni 151840
    suppress-arp
    ingress-replication protocol bgp
  member vni 151842
    suppress-arp
    ingress-replication protocol bgp
  member vni 151854
    suppress-arp
    ingress-replication protocol bgp
  member vni 152142
    suppress-arp
    ingress-replication protocol bgp
  member vni 152340
    suppress-arp
    ingress-replication protocol bgp
  member vni 152343
    suppress-arp
    ingress-replication protocol bgp
  member vni 152372
    suppress-arp
    ingress-replication protocol bgp
  member vni 152375
    suppress-arp
    ingress-replication protocol bgp
  member vni 152392
    suppress-arp
    ingress-replication protocol bgp
  member vni 152440
    suppress-arp
    ingress-replication protocol bgp
  member vni 152633
    suppress-arp
    ingress-replication protocol bgp
  member vni 152640
    suppress-arp
    ingress-replication protocol bgp
  member vni 152642
    suppress-arp
    ingress-replication protocol bgp
  member vni 152661
    suppress-arp
    ingress-replication protocol bgp
  member vni 152751
    suppress-arp
    ingress-replication protocol bgp
  member vni 152759
    suppress-arp
    ingress-replication protocol bgp
  member vni 152774
    suppress-arp
    ingress-replication protocol bgp
  member vni 152867
    suppress-arp
    ingress-replication protocol bgp
  member vni 153142
    suppress-arp
    ingress-replication protocol bgp
  member vni 153149
    suppress-arp
    ingress-replication protocol bgp
  member vni 153340
    suppress-arp
    ingress-replication protocol bgp
  member vni 153342
    suppress-arp
    ingress-replication protocol bgp
  member vni 153372
    suppress-arp
    ingress-replication protocol bgp
  member vni 153392
    suppress-arp
    ingress-replication protocol bgp
  member vni 153440
    suppress-arp
    ingress-replication protocol bgp

interface Ethernet1/1
  description ***Lilltle-Boys***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1392,2392,3392
  spanning-tree bpduguard enable
  spanning-tree guard root
  no shutdown

interface Ethernet1/2
  description ***Raiayn-SW**
  switchport
  switchport mode trunk
  spanning-tree cost 65535
  no shutdown

interface Ethernet1/3
  description ***N.Gonj-Mikrotik**
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1096,1440,1640,2440,3440
  no shutdown

interface Ethernet1/4
  description ***StarGate-NG***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1222,2633,2774
  no shutdown

interface Ethernet1/5
  description ***FiberX***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1013,1342,1398,1813,1842,2013,2342,2642,2661,2813,2913,3213,3342
  no shutdown

interface Ethernet1/6
  description ***Faiza-SW***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/7
  description ***TFN-BKP**
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1340,1840,2340,2640,3340
  no shutdown

interface Ethernet1/8
  description ***turjo-comm***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1491,1775,2375,3149
  spanning-tree bpduguard enable
  spanning-tree guard root
  no shutdown

interface Ethernet1/9
  description ***Dhaka-Net***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1337,1772,2372,2751,3372
  no shutdown

interface Ethernet1/10
  description ***OMM-IT-Network**
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1142,1854,2142,2759,2867,3142
  speed 1000
  no shutdown

interface Ethernet1/11
  description ***Health-Hospital***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 805-808,1440
  speed 1000
  no shutdown

interface Ethernet1/12
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/13
  no shutdown

interface Ethernet1/14
  no shutdown

interface Ethernet1/15
  no shutdown

interface Ethernet1/16
  no shutdown

interface Ethernet1/17
  no shutdown

interface Ethernet1/18
  no shutdown

interface Ethernet1/19
  no shutdown

interface Ethernet1/20
  no shutdown

interface Ethernet1/21
  no shutdown

interface Ethernet1/22
  no shutdown

interface Ethernet1/23
  no shutdown

interface Ethernet1/24
  no shutdown

interface Ethernet1/25
  no shutdown

interface Ethernet1/26
  no shutdown

interface Ethernet1/27
  no shutdown

interface Ethernet1/28
  no shutdown

interface Ethernet1/29
  no shutdown

interface Ethernet1/30
  no shutdown

interface Ethernet1/31
  no shutdown

interface Ethernet1/32
  no shutdown

interface Ethernet1/33
  no shutdown

interface Ethernet1/34
  no shutdown

interface Ethernet1/35
  no shutdown

interface Ethernet1/36
  no shutdown

interface Ethernet1/37
  no shutdown

interface Ethernet1/38
  no shutdown

interface Ethernet1/39
  no shutdown

interface Ethernet1/40
  no shutdown

interface Ethernet1/41
  no shutdown

interface Ethernet1/42
  no shutdown

interface Ethernet1/43
  no shutdown

interface Ethernet1/44
  no shutdown

interface Ethernet1/45
  no shutdown

interface Ethernet1/46
  no shutdown

interface Ethernet1/47
  no shutdown

interface Ethernet1/48
  no shutdown

interface Ethernet1/49
  description ***Fatullah-SW***
  switchport
  switchport mode trunk
  spanning-tree cost 1
  no shutdown

interface Ethernet1/50
  description ***BKB***
  switchport
  switchport mode trunk
  spanning-tree cost 2000
  no shutdown

interface Ethernet1/51
  description ***Jhalkuri-Link**
  switchport
  switchport mode trunk
  spanning-tree cost 2
  no shutdown

interface Ethernet1/52
  no shutdown

interface Ethernet1/53
  no shutdown

interface Ethernet1/54
  no shutdown

interface Ethernet1/55
  no shutdown

interface Ethernet1/56
  no shutdown

interface Ethernet1/57
  no shutdown

interface Ethernet1/58
  no shutdown

interface Ethernet1/59
  no shutdown

interface Ethernet1/60
  no shutdown

interface mgmt0
  vrf member management
line console
line vty
boot nxos bootflash:/nxos64-cs.10.3.1.F.bin
evpn
  vni 15805 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 15806 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 15807 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 15808 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151096 l2
    route-target import auto
    route-target export auto
  vni 151142 l2
    route-target import auto
    route-target export auto
  vni 151222 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151337 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151340 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151342 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151392 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151398 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151440 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151491 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151640 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151772 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151775 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151840 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151842 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 151854 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152142 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152340 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152343 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152372 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152375 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152392 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152440 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152633 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152640 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152642 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152661 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152751 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152759 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152774 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 152867 l2
    route-target import auto
    route-target export auto
  vni 153142 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 153149 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 153340 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 153342 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 153372 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 153392 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 153440 l2
    rd auto
    route-target import auto
    route-target export auto



Narayangong-SW#