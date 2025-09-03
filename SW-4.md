BKB# show running-config

!Command: show running-config
!Running configuration last done at: Wed Aug 27 02:35:17 2025
!Time: Mon Sep  1 14:10:13 2025

version 10.3(1) Bios:version 05.47 [last: 05.28]
hostname BKB
vdc BKB id 1
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

username admin password 5 $5$SxL6BgCc$4vRMjlqBGs2.reXc8fowfio3aRDjDRb3vNJ1kLiN2z7  role network-admin
ip domain-lookup
copp profile strict
snmp-server user admin network-admin auth md5 0xd5b710c5edadea4dfe623f635f8e22fe priv des 0xd5b710c5edadea4dfe623f635f8e22fe localizedkey
rmon event 1 description FATAL(1) owner PMON@FATAL
rmon event 2 description CRITICAL(2) owner PMON@CRITICAL
rmon event 3 description ERROR(3) owner PMON@ERROR
rmon event 4 description WARNING(4) owner PMON@WARNING
rmon event 5 description INFORMATION(5) owner PMON@INFO
no snmp-server enable traps entity entity_mib_change
no snmp-server enable traps entity entity_module_status_change
no snmp-server enable traps entity entity_power_status_change
no snmp-server enable traps entity entity_module_inserted
no snmp-server enable traps entity entity_module_removed
no snmp-server enable traps entity entity_unrecognised_module
no snmp-server enable traps entity entity_fan_status_change
no snmp-server enable traps entity entity_power_out_change
no snmp-server enable traps link linkDown
no snmp-server enable traps link linkUp
no snmp-server enable traps link extended-linkDown
no snmp-server enable traps link extended-linkUp
no snmp-server enable traps link cieLinkDown
no snmp-server enable traps link cieLinkUp
no snmp-server enable traps link delayed-link-state-change
no snmp-server enable traps rf redundancy_framework
no snmp-server enable traps license notify-license-expiry
no snmp-server enable traps license notify-no-license-for-feature
no snmp-server enable traps license notify-licensefile-missing
no snmp-server enable traps license notify-license-expiry-warning
no snmp-server enable traps upgrade UpgradeOpNotifyOnCompletion
no snmp-server enable traps upgrade UpgradeJobStatusNotify
no snmp-server enable traps rmon risingAlarm
no snmp-server enable traps rmon fallingAlarm
no snmp-server enable traps rmon hcRisingAlarm
no snmp-server enable traps rmon hcFallingAlarm
no snmp-server enable traps entity entity_sensor
no snmp-server enable traps entity cefcMIBEnableStatusNotification
no snmp-server enable traps generic coldStart
no snmp-server enable traps generic warmStart
no snmp-server enable traps storm-control cpscEventRev1
no snmp-server enable traps link cErrDisableInterfaceEventRev1
no snmp-server enable traps link cmn-mac-move-notification
snmp-server community Speed group network-operator

ip route 0.0.0.0/0 172.16.100.1
vlan 1-3967
vlan 1060
  vn-segment 131060
vlan 2221
  vn-segment 132221
vlan 3002
  vn-segment 133002

vrf context management

interface Vlan1

interface Vlan3100
  no shutdown
  ip address 172.16.100.243/24

interface port-channel1
  description ***BKB-LACP***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1060,2221

interface nve1
  no shutdown
  host-reachability protocol bgp
  source-interface loopback0
  member vni 131060
    suppress-arp
    ingress-replication protocol bgp
  member vni 132221
    suppress-arp
    ingress-replication protocol bgp
  member vni 133002
    suppress-arp
    ingress-replication protocol bgp

interface Ethernet1/1

interface Ethernet1/2
  description ***Rayan-SW***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/3
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1060,2221
  no shutdown

interface Ethernet1/4
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1060,2221
  no shutdown

interface Ethernet1/5
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1060,2221
  no shutdown

interface Ethernet1/6
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/7
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/8

interface Ethernet1/9

interface Ethernet1/10

interface Ethernet1/11

interface Ethernet1/12
  description ****BKB-BDIX***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 3002
  no shutdown

interface Ethernet1/13

interface Ethernet1/14

interface Ethernet1/15

interface Ethernet1/16

interface Ethernet1/17

interface Ethernet1/18
  description ***BKB-LACP***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1060,2221
  channel-group 1 mode active
  no shutdown

interface Ethernet1/19
  description ***BKB-LACP***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1060,2221
  channel-group 1 mode active
  no shutdown

interface Ethernet1/20
  description ***BKB-LACP***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1,1060,2221
  channel-group 1 mode active
  no shutdown

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

interface Ethernet1/41

interface Ethernet1/42

interface Ethernet1/43

interface Ethernet1/44

interface Ethernet1/45

interface Ethernet1/46

interface Ethernet1/47

interface Ethernet1/48

interface Ethernet1/49
  description ***Advanced-LInk***
  switchport
  switchport mode trunk
  spanning-tree cost 1
  no shutdown

interface Ethernet1/50
  description ***Narayangong-Link***
  switchport
  switchport mode trunk
  spanning-tree cost 2000
  no shutdown

interface Ethernet1/51

interface Ethernet1/52

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
  vni 131060 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 132221 l2
    rd auto
    route-target import auto
    route-target export auto
  vni 133002 l2
    route-target import auto
    route-target export auto



BKB#
