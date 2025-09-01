kazla_nexus# show running-config

!Command: show running-config
!Time: Mon Sep  1 11:05:51 2025

version 7.0(3)I4(7)
hostname kazla_nexus
vdc kazla_nexus id 1
  limit-resource vlan minimum 16 maximum 4094
  limit-resource vrf minimum 2 maximum 4096
  limit-resource port-channel minimum 0 maximum 511
  limit-resource u4route-mem minimum 248 maximum 248
  limit-resource u6route-mem minimum 96 maximum 96
  limit-resource m4route-mem minimum 58 maximum 58
  limit-resource m6route-mem minimum 8 maximum 8

feature telnet
feature interface-vlan
feature lacp
feature lldp

username admin password 5 $5$LPDJKE$8oTUW6Ql1Fej/IyC0ufaQd4Jfv33hsOLpoiSSasnsR2  role network-admin
ip domain-lookup
copp profile strict
rmon event 1 log trap public description FATAL(1) owner PMON@FATAL
rmon event 2 log trap public description CRITICAL(2) owner PMON@CRITICAL
rmon event 3 log trap public description ERROR(3) owner PMON@ERROR
rmon event 4 log trap public description WARNING(4) owner PMON@WARNING
rmon event 5 log trap public description INFORMATION(5) owner PMON@INFO
snmp-server community Speed group network-operator
snmp-server community secret group network-operator

vlan 1-3967

vrf context management
  ip route 0.0.0.0/0 10.112.207.126
hardware profile portmode 48x25G+4x100G



interface Vlan1

interface Vlan3836
  no shutdown
  no ip redirects
  ip address 10.70.0.2/30
  ip address 172.16.183.246/30 secondary

interface port-channel2
  description ***F@H-100G***
  switchport
  switchport mode trunk
  spanning-tree cost 1
  mtu 9216

interface port-channel5
  description ***LACP-WITH-PTX***
  switchport
  switchport mode trunk
  mtu 9216

interface port-channel6
  description ***Potato-Bundle***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 370-373,381-385,462,470-473,556,901-905,960-964,1011,1016,1081,1091,1102-1103,1178,1331,1388,1408,1608,1731,18
12,1882,1987,2094,2178,2331,2408,2651-2652,2658,2768,3044,3178,3331,3492
  spanning-tree guard root
  spanning-tree bpdufilter enable
  mtu 9216

interface port-channel20
  description ***Potatao-100G-Bundle***
  switchport
  switchport mode trunk
  mtu 9216

interface Ethernet1/1

interface Ethernet1/2

interface Ethernet1/3

interface Ethernet1/4

interface Ethernet1/5

interface Ethernet1/6

interface Ethernet1/7

interface Ethernet1/8

interface Ethernet1/9

interface Ethernet1/10
  description ***BSCCL-MOGBAZAR-END***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 700-703,850-853,885-888,1150-1152,2132
  spanning-tree guard root
  spanning-tree bpdufilter enable
  no shutdown

interface Ethernet1/11
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/12
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active

interface Ethernet1/13
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/14
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/15
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/16
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/17
  description ***F@H-100G****
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/18
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active

interface Ethernet1/19
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/20
  description ***F@H-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 2 mode active
  no shutdown

interface Ethernet1/21
  description **POTATO-DATA-MIKROTIK**
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,381-385,452,462,1016,1812,2094,2652,3492
  no shutdown

interface Ethernet1/22

interface Ethernet1/23
  description ***T-Corp***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/24

interface Ethernet1/25
  description ****Munna-MKT****
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 458
  spanning-tree guard root
  spanning-tree bpdufilter enable
  no shutdown

interface Ethernet1/26

interface Ethernet1/27
  description ***Potato-Data-Client**
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 452,458
  no shutdown

interface Ethernet1/28
  description SPEED-ONLINE-CORE
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/29

interface Ethernet1/30

interface Ethernet1/31

interface Ethernet1/32

interface Ethernet1/33
  description ***LANCACHE***
  switchport
  switchport access vlan 386
  no shutdown

interface Ethernet1/34
  description ***Nex-Kazla-New-RTR***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2-4094
  no shutdown

interface Ethernet1/35

interface Ethernet1/36

interface Ethernet1/37

interface Ethernet1/38
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/39

interface Ethernet1/40
  description ***NetX-Kazla-RTR***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/41
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/42
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/43
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/44
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/45

interface Ethernet1/46
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2-3967
  no shutdown

interface Ethernet1/47
  description ***ICMP-RTR***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2-4094
  no shutdown

interface Ethernet1/48

interface Ethernet1/49
  description ****Potato-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 20 mode active
  no shutdown

interface Ethernet1/50
  description ***Kazla-mx-204***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/51
  description ***Potato-100G***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 20 mode active
  no shutdown

interface Ethernet1/52
  description ***Kazla-PTX***
  switchport
  switchport mode trunk
  mtu 9216
  channel-group 5 mode active
  no shutdown

interface mgmt0
  vrf member management
  ip address 10.112.207.20/25
line console
line vty
boot nxos bootflash:/nxos.7.0.3.I4.7.bin
ip route 0.0.0.0/0 172.16.183.245


kazla_nexus#
