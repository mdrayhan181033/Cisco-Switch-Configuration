ADVANCE-SW# show running-config

!Command: show running-config
!Running configuration last done at: Fri Aug 29 18:41:48 2025
!Time: Sun Aug 31 15:54:12 2025

version 10.3(1) Bios:version 05.47 [last: 05.28]
hostname ADVANCE-SW
vdc ADVANCE-SW id 1
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
feature fabric forwarding
feature interface-vlan
feature vn-segment-vlan-based
feature lacp
feature lldp
feature bfd
feature nv overlay

no password strength-check
username admin password 5 $5$Gzw3krAv$RyCpNhUNto7FK6bLTVaZ.6bYulymoUrmqgxMP5ZmN/3  role network-admin
ip domain-lookup
copp profile strict
snmp-server user admin network-admin auth md5 0xbf30e5192ea42806f331cd6233e13734 priv des 0xbf30e5192ea42806f331cd6233e13734 localizedkey
rmon event 1 description FATAL(1) owner PMON@FATAL
rmon event 2 description CRITICAL(2) owner PMON@CRITICAL
rmon event 3 description ERROR(3) owner PMON@ERROR
rmon event 4 description WARNING(4) owner PMON@WARNING
rmon event 5 description INFORMATION(5) owner PMON@INFO
snmp-server community Speed group network-operator
system default switchport

ip route 0.0.0.0/0 172.16.100.1
ip pim rp-address 10.12.4.1 group-list 224.0.0.0/4
ip pim ssm range 232.0.0.0/8
ip pim anycast-rp 10.12.4.1 10.12.0.1
ip pim anycast-rp 10.12.4.1 10.12.0.2
ip pim anycast-rp 10.12.4.1 10.12.0.3
vlan 1-3955
vlan 1031
  vn-segment 111031
vlan 1357
  vn-segment 111357
vlan 1368
  vn-segment 111368
vlan 1399
  vn-segment 111399
vlan 1450
  vn-segment 111450
vlan 1650
  vn-segment 111650
vlan 1689
  vn-segment 111689
vlan 1708
  vn-segment 111708
vlan 1768
  vn-segment 111768
vlan 1885
  vn-segment 111885
vlan 2031
  vn-segment 112031
vlan 2308
  vn-segment 112308
vlan 2316
  vn-segment 112316
vlan 2368
  vn-segment 112368
vlan 2450
  vn-segment 112450
vlan 2489
  vn-segment 112489
vlan 2504
  vn-segment 112504
vlan 2505
  vn-segment 112505
vlan 2506
  vn-segment 112506
vlan 2656
  vn-segment 112656
vlan 2680
  vn-segment 112680
vlan 2719
  vn-segment 112719
vlan 2747
  vn-segment 112747
vlan 2788
  vn-segment 112788
vlan 3017
  vn-segment 113017
vlan 3020
  vn-segment 113020
vlan 3100
  name mgmt
vlan 3196
  vn-segment 113196
vlan 3368
  vn-segment 113368
vlan 3450
  vn-segment 113450
vlan 3489
  vn-segment 113489

vrf context management

interface Vlan1

interface Vlan3100
  no shutdown
  ip address 172.16.100.250/24

interface nve1
  no shutdown
  host-reachability protocol bgp
  source-interface loopback0
  member vni 111031
    suppress-arp
    ingress-replication protocol bgp
  member vni 111357
    suppress-arp
    ingress-replication protocol bgp
  member vni 111368
    suppress-arp
    ingress-replication protocol bgp
  member vni 111399
    suppress-arp
    ingress-replication protocol bgp
  member vni 111450
    suppress-arp
    ingress-replication protocol bgp
  member vni 111650
    suppress-arp
    ingress-replication protocol bgp
  member vni 111689
    suppress-arp
    ingress-replication protocol bgp
  member vni 111708
    suppress-arp
    ingress-replication protocol bgp
  member vni 111768
    suppress-arp
    ingress-replication protocol bgp
  member vni 111885
    suppress-arp
    ingress-replication protocol bgp
  member vni 112031
    suppress-arp
    ingress-replication protocol bgp
  member vni 112308
    suppress-arp
    ingress-replication protocol bgp
  member vni 112316
    suppress-arp
    ingress-replication protocol bgp
  member vni 112368
    suppress-arp
    ingress-replication protocol bgp
  member vni 112450
    suppress-arp
    ingress-replication protocol bgp
  member vni 112489
    suppress-arp
    ingress-replication protocol bgp
  member vni 112504
    suppress-arp
    ingress-replication protocol bgp
  member vni 112505
    suppress-arp
    ingress-replication protocol bgp
  member vni 112506
    suppress-arp
    ingress-replication protocol bgp
  member vni 112656
    suppress-arp
    ingress-replication protocol bgp
  member vni 112680
    suppress-arp
    ingress-replication protocol bgp
  member vni 112719
    suppress-arp
    ingress-replication protocol bgp
  member vni 112747
    suppress-arp
    ingress-replication protocol bgp
  member vni 112788
    suppress-arp
    ingress-replication protocol bgp
  member vni 113017
    suppress-arp
    ingress-replication protocol bgp
  member vni 113020
    suppress-arp
    ingress-replication protocol bgp
  member vni 113196
    suppress-arp
    ingress-replication protocol bgp
  member vni 113368
    suppress-arp
    ingress-replication protocol bgp
  member vni 113450
    suppress-arp
    ingress-replication protocol bgp
  member vni 113489
    suppress-arp
    ingress-replication protocol bgp

interface Ethernet1/1
  description **SUPER-ZONE**
  switchport mode trunk
  switchport trunk allowed vlan 1368,1768,2368,2788,3368
  no shutdown

interface Ethernet1/2
  description **ZAZIRA-ONLINE**
  switchport mode trunk
  switchport trunk allowed vlan 1450,1650,2450,2747,3450
  no shutdown

interface Ethernet1/3
  description **SHANARPAR-CYBER-NET**
  switchport mode trunk
  switchport trunk allowed vlan 1357,1689,2316,2489,3489
  no shutdown

interface Ethernet1/4
  description **ABCD-ONLINE-PRI**
  switchport mode trunk
  switchport trunk allowed vlan 1031,1885,2031,2719,3196
  no shutdown

interface Ethernet1/5
  description **ADVANCE**
  switchport mode trunk
  switchport trunk allowed vlan 1399,1708,2308,2680,3029
  no shutdown

interface Ethernet1/6
  description **FAIR-ONLINE**
  switchport mode trunk
  switchport trunk allowed vlan 2504-2506,2656,3017
  no shutdown

interface Ethernet1/7

interface Ethernet1/8

interface Ethernet1/9

interface Ethernet1/10

interface Ethernet1/11

interface Ethernet1/12

interface Ethernet1/13

interface Ethernet1/14

interface Ethernet1/15
  no shutdown

interface Ethernet1/16

interface Ethernet1/17

interface Ethernet1/18

interface Ethernet1/19

interface Ethernet1/20

interface Ethernet1/21

interface Ethernet1/22

interface Ethernet1/23

interface Ethernet1/24

interface Ethernet1/25

interface Ethernet1/26

interface Ethernet1/27

interface Ethernet1/28

interface Ethernet1/29

interface Ethernet1/30

interface Ethernet1/31

interface Ethernet1/32

interface Ethernet1/33

interface Ethernet1/34

interface Ethernet1/35

interface Ethernet1/36

interface Ethernet1/37

interface Ethernet1/38

interface Ethernet1/39

interface Ethernet1/40
  no shutdown

interface Ethernet1/41

interface Ethernet1/42

interface Ethernet1/43

interface Ethernet1/44

interface Ethernet1/45

interface Ethernet1/46

interface Ethernet1/47

interface Ethernet1/48
  description **POTATO-DATA**
  switchport mode trunk
  speed 1000
  no shutdown

interface Ethernet1/49
  description **KAZLA-POP**
  switchport mode trunk
  spanning-tree cost 1
  no shutdown

interface Ethernet1/50
  description **BKB-POP**
  switchport mode trunk
  no shutdown

interface Ethernet1/51

interface Ethernet1/52

interface Ethernet1/53

interface Ethernet1/54

interface Ethernet1/55

interface Ethernet1/56

interface Ethernet1/57

interface Ethernet1/58

interface Ethernet1/59

interface Ethernet1/60

interface mgmt0
  vrf member management

interface loopback0
  ip address 10.12.0.2/32
  ip router ospf 1 area 0.0.0.0
  ip pim sparse-mode

interface loopback1
  ip address 10.12.4.2/32
  ip router ospf 1 area 0.0.0.0
  ip pim sparse-mode
line console
line vty
boot nxos bootflash:/nxos64-cs.10.3.1.F.bin
router ospf 1
  bfd
  router-id 10.12.0.2
  max-metric router-lsa on-startup wait-for bgp 64512
router bgp 64512
  router-id 10.12.0.2
  address-family ipv4 unicast
  address-family l2vpn evpn
  neighbor 10.12.0.1
    remote-as 64512
    update-source loopback0
    address-family ipv4 unicast
      send-community
      send-community extended
      next-hop-self
      soft-reconfiguration inbound always
    address-family l2vpn evpn
      send-community
      send-community extended
  neighbor 10.12.0.3
    remote-as 64512
    update-source loopback0
    address-family ipv4 unicast
      send-community
      send-community extended
      next-hop-self
      soft-reconfiguration inbound always
evpn
  vni 111031 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111357 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111368 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111399 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111450 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111650 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111689 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111708 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111768 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 111885 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112031 l2
    route-target import auto
    route-target export auto
  vni 112308 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112316 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112368 l2
    rd auto
    route-target import auto
  vni 112450 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112489 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112504 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112505 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112506 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112656 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112680 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112719 l2
    route-target import auto
    route-target export auto
  vni 112747 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 112788 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 113017 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 113020 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 113196 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 113368 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 113450 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 113489 l2
    rd auto
    route-target import auto
    route-target export auto

ADVANCE-SW#