!Command: show running-config
!Running configuration last done at: Sat Aug 23 13:47:46 2025
!Time: Mon Aug 25 04:00:00 2025

version 10.3(1) Bios:version 05.47 [last: 05.28]
hostname SIGNBOARD-SW
vdc SIGNBOARD-SW id 1
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
username admin password 5 $5$IQEW335W$.9tFKYIVeXspzAYup/pQ69bpODly5A6I8/PW6aLkGvA  role network-admin
ip domain-lookup
copp profile strict
snmp-server user admin network-admin auth md5 0x28d79195363b85448cbf588e28cccb07 priv des 0x28d79195363b85448cbf588e28cccb07 localizedkey
rmon event 1 description FATAL(1) owner PMON@FATAL
rmon event 2 description CRITICAL(2) owner PMON@CRITICAL
rmon event 3 description ERROR(3) owner PMON@ERROR
rmon event 4 description WARNING(4) owner PMON@WARNING
rmon event 5 description INFORMATION(5) owner PMON@INFO
snmp-server community Speed group network-operator

ip route 0.0.0.0/0 172.16.100.1
ip pim rp-address 10.12.4.1 group-list 224.0.0.0/4
ip pim ssm range 232.0.0.0/8
ip pim anycast-rp 10.12.4.1 10.12.0.1
ip pim anycast-rp 10.12.4.1 10.12.0.2
ip pim anycast-rp 10.12.4.1 10.12.0.3
vlan 1-3967
vlan 1026
  vn-segment 121026
vlan 1201
  vn-segment 121201
vlan 1258
  vn-segment 121258
vlan 1281
  vn-segment 121281
vlan 1301
  vn-segment 121301
vlan 1339
  vn-segment 121339
vlan 1345
  vn-segment 121345
vlan 1354
  vn-segment 121354
vlan 1401
  vn-segment 121501
vlan 1467
  vn-segment 121467
vlan 1667
  vn-segment 121667
vlan 1739
  vn-segment 121739
vlan 1745
  vn-segment 121745
vlan 1754
  vn-segment 121754
vlan 1756
  vn-segment 121756
vlan 1824
  vn-segment 121824
vlan 1992
  vn-segment 121992
vlan 2026
  vn-segment 122026
vlan 2104
  vn-segment 122104
vlan 2281
  vn-segment 122281
vlan 2339
  vn-segment 122339
vlan 2345
  vn-segment 122345
vlan 2354
  vn-segment 122354
vlan 2467
  vn-segment 122467
vlan 2692
  vn-segment 122692
vlan 2720
  vn-segment 122720
vlan 2739
  vn-segment 122739
vlan 2743
  vn-segment 122743
vlan 2771
  vn-segment 122771
vlan 2789
  vn-segment 122789
vlan 3026
  vn-segment 123026
vlan 3031
  vn-segment 123031
vlan 3098
  vn-segment 123098
vlan 3100
  name mgmt
vlan 3281
  vn-segment 123281
vlan 3339
  vn-segment 123339
vlan 3345
  vn-segment 123345
vlan 3354
  vn-segment 123354

vrf context management

interface Vlan1

interface Vlan3100
  no shutdown
  ip address 172.16.100.247/24

interface port-channel1
  description ***F@H-UG-Link***
  switchport
  switchport mode trunk

interface nve1
  no shutdown
  host-reachability protocol bgp
  source-interface loopback0
  member vni 121026
    suppress-arp
    ingress-replication protocol bgp
  member vni 121201
    suppress-arp
    ingress-replication protocol bgp
  member vni 121258
    suppress-arp
    ingress-replication protocol bgp
  member vni 121281
    suppress-arp
    ingress-replication protocol bgp
  member vni 121301
    suppress-arp
    ingress-replication protocol bgp
  member vni 121339
    suppress-arp
    ingress-replication protocol bgp
  member vni 121345
    suppress-arp
    ingress-replication protocol bgp
  member vni 121354
    suppress-arp
    ingress-replication protocol bgp
  member vni 121467
    suppress-arp
    ingress-replication protocol bgp
  member vni 121501
    suppress-arp
    ingress-replication protocol bgp
  member vni 121667
    suppress-arp
    ingress-replication protocol bgp
  member vni 121739
    suppress-arp
    ingress-replication protocol bgp
  member vni 121745
    suppress-arp
    ingress-replication protocol bgp
  member vni 121754
    suppress-arp
    ingress-replication protocol bgp
  member vni 121756
    suppress-arp
    ingress-replication protocol bgp
  member vni 121824
    suppress-arp
    ingress-replication protocol bgp
  member vni 121992
    suppress-arp
    ingress-replication protocol bgp
  member vni 122026
    suppress-arp
    ingress-replication protocol bgp
  member vni 122104
    suppress-arp
    ingress-replication protocol bgp
  member vni 122281
    suppress-arp
    ingress-replication protocol bgp
  member vni 122339
    suppress-arp
    ingress-replication protocol bgp
  member vni 122345
    suppress-arp
    ingress-replication protocol bgp
  member vni 122354
    suppress-arp
    ingress-replication protocol bgp
  member vni 122467
    suppress-arp
    ingress-replication protocol bgp
  member vni 122692
    suppress-arp
    ingress-replication protocol bgp
  member vni 122720
    suppress-arp
    ingress-replication protocol bgp
  member vni 122739
    suppress-arp
    ingress-replication protocol bgp
  member vni 122743
    suppress-arp
    ingress-replication protocol bgp
  member vni 122771
    suppress-arp
    ingress-replication protocol bgp
  member vni 122789
    suppress-arp
    ingress-replication protocol bgp
  member vni 123026
    suppress-arp
    ingress-replication protocol bgp
  member vni 123031
    suppress-arp
    ingress-replication protocol bgp
  member vni 123098
    suppress-arp
    ingress-replication protocol bgp
  member vni 123281
    suppress-arp
    ingress-replication protocol bgp
  member vni 123339
    suppress-arp
    ingress-replication protocol bgp
  member vni 123345
    suppress-arp
    ingress-replication protocol bgp
  member vni 123354
    suppress-arp
    ingress-replication protocol bgp

interface Ethernet1/1

interface Ethernet1/2
  description ***Bhuighor-Akash***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1201,1301,1401,1501
  no shutdown

interface Ethernet1/3

interface Ethernet1/4
  description ***MAHMUDPUR-POP***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/5

interface Ethernet1/6
  description ***JItu-Network***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1354,1754,2354,2771,3354
  no shutdown

interface Ethernet1/7
  description ***Appyon-Online***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1026,1824,2026,2692,3026
  no shutdown

interface Ethernet1/8
  description ***Green-Touch***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1281,1992,2281,2743,3281
  no shutdown

interface Ethernet1/9

interface Ethernet1/10
  description ***Super-Zone***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1345,1745,2345,2789,3345
  no shutdown

interface Ethernet1/11
  description ***Pulok-buijhor***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1258,1756,2104,3098
  no shutdown

interface Ethernet1/12
  description ***F@HOME BKP ***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  no shutdown

interface Ethernet1/13
  description ***ABCD-ONLINE-BKP***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1467,1667,2467,2720,3031
  no shutdown

interface Ethernet1/14
  description ***F@HOME***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 1 mode active
  no shutdown

interface Ethernet1/15
  description ***Zara-Communication***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1339,1739,2339,2739,3339
  no shutdown

interface Ethernet1/16
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/17
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/18
  switchport
  switchport mode trunk
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
  switchport
  switchport mode trunk
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
  description ***Kazla-UPLINK***
  switchport
  switchport mode trunk
  spanning-tree cost 1
  no shutdown

interface Ethernet1/50
  description ***Jalkuri-SW***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/51
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
  vni 121026 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121201 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121258 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121281 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121301 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121339 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121345 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121354 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121467 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121501 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121667 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121739 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121745 l2
    rd auto
    route-target import auto
  vni 121754 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121756 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 121824 l2
    rd auto
    route-target import auto
  vni 121992 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122026 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122104 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122281 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122339 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122345 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122354 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122467 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122692 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122720 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122739 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122743 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122771 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 122789 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 123026 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 123031 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 123098 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 123281 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 123339 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 123345 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 123354 l2
    rd auto
    route-target import auto
    route-target export auto



SIGNBOARD-SW#
