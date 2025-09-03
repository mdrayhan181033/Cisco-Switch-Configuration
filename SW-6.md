Upstream-Core-SW# show running-config

!Command: show running-config
!Running configuration last done at: Wed Sep  3 07:25:22 2025
!Time: Wed Sep  3 13:02:00 2025

version 9.3(11) Bios:version 05.47
hostname Upstream-Core-SW
vdc Upstream-Core-SW id 1
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
feature vtp

no password strength-check
username admin password 5 $5$MNABCL$spiEpg7ZPDMlLbybdTkgMvg4p1oVYLD3yguZV9IcQD7  role network-admin
username netx password 5 !  role network-operator
username netx passphrase  lifetime 99999 warntime 14 gracetime 3
ip domain-lookup
copp profile strict
snmp-server user admin network-admin auth md5 0xde8d8f66dd3a2b5fa21c05ae49a578df priv 0xde8d8f66dd3a2b5fa21c05ae49a578df localizedkey
rmon event 1 description FATAL(1) owner PMON@FATAL
rmon event 2 description CRITICAL(2) owner PMON@CRITICAL
rmon event 3 description ERROR(3) owner PMON@ERROR
rmon event 4 description WARNING(4) owner PMON@WARNING
rmon event 5 description INFORMATION(5) owner PMON@INFO
snmp-server community Speed group network-operator

ip route 0.0.0.0/0 172.16.189.41
system vlan long-name
vlan 1-3967

vrf context management
  ip route 0.0.0.0/0 10.112.207.126

interface Vlan1
  no shutdown

interface Vlan3901
  no shutdown
  ip address 172.16.189.42/30

interface port-channel1
  switchport
  switchport mode trunk

interface port-channel2
  description ***F@H-NTTN-Link***
  switchport
  switchport mode trunk

interface port-channel3
  description ***REGO-NTTN-SW***
  switchport
  switchport mode trunk
  spanning-tree port type edge

interface port-channel4
  description ***SR-COM-SW***
  switchport
  switchport mode trunk
  spanning-tree port type edge

interface port-channel5
  description ***FHL***
  switchport
  switchport mode trunk

interface port-channel6
  description ***Bahon-NTTN***
  switchport
  switchport mode trunk

interface port-channel7
  description ***GFCL_bundle***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 634,643,713,735,1652,1831,1849,2078,2157

interface port-channel8
  description ***Hello-Tech***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2217-2218,2398
  spanning-tree port type edge

interface Ethernet1/1
  description ***NETX-Core-Super-MKT**
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/2
  description ***NTTN-Access-RTR***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/3
  description ***SR-COM-SW***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 4 mode active
  no shutdown

interface Ethernet1/4
  description ***BDMAX***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/5
  description **FHL-NTTN**
  switchport
  switchport mode trunk
  channel-group 5 mode active
  no shutdown

interface Ethernet1/6
  description ***Kazla-204**
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1185,1904,2185,2764,3185
  no shutdown

interface Ethernet1/7
  description ***InfoTech-Dhaka-RTR***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1417,1717,1900-1904,2417,2617,2619,3317,3531-3535
  no shutdown

interface Ethernet1/8
  description ***EXABYTE-NTTN-SCL***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2845-2849,2880-2884,3531-3535,3538-3542,3631-3635,3674-3685,3691-3695,3991-3995
  no shutdown

interface Ethernet1/9

interface Ethernet1/10
  description ***Net-Expert-BD***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2720
  no shutdown

interface Ethernet1/11

interface Ethernet1/12

interface Ethernet1/13

interface Ethernet1/14

interface Ethernet1/15

interface Ethernet1/16

interface Ethernet1/17

interface Ethernet1/18

interface Ethernet1/19

interface Ethernet1/20
  switchport
  switchport mode trunk
  spanning-tree guard root
  spanning-tree bpdufilter enable

interface Ethernet1/21

interface Ethernet1/22
  no shutdown

interface Ethernet1/23
  description ***GFCL-BKP***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 634,643,713,735,1652,1831,1849,2078,2157
  channel-group 7 mode active
  no shutdown

interface Ethernet1/24
  description ***GFCL***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 634,643,713,735,1652,1831,1849,2078,2157
  channel-group 7 mode active
  no shutdown

interface Ethernet1/25
  description ***STL-NTTN-SW***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/26
  description ***NRB-MX204***
  switchport
  switchport mode trunk
  no shutdown

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
  description ***REGO-NTTN-SW***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 3 mode active
  no shutdown

interface Ethernet1/41
  description ***REGO-NTTN-SW***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 3 mode active
  no shutdown

interface Ethernet1/42
  description ***REGO-NTTN-SW***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 3 mode active
  no shutdown

interface Ethernet1/43
  description ***REGO-NTTN-SW***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 3 mode active
  no shutdown

interface Ethernet1/44

interface Ethernet1/45

interface Ethernet1/46

interface Ethernet1/47
  description ***Bahon-NTTN***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 6 mode active
  no shutdown

interface Ethernet1/48
  description ***Bahon-NTTN***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 6 mode active
  no shutdown

interface Ethernet1/49
  description ***F@H-NTTN-Link***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 2 mode active
  no shutdown

interface Ethernet1/50
  description ***F@H-NTTN-Link***
  switchport
  switchport mode trunk
  spanning-tree port type edge
  channel-group 2 mode active
  no shutdown

interface Ethernet1/51
  description ***PTX-et-0/0/1**
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/52
  description ***NRB-204***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/53
  description ***Mime-Sec-Link***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 1203,2070,2348
  spanning-tree guard root
  spanning-tree bpdufilter enable
  no shutdown

interface Ethernet1/54
  description ***Hello-Tech***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2217-2218,2398
  channel-group 8 mode active
  no shutdown

interface Ethernet1/55
  description ***Hello-Tech***
  switchport
  switchport mode trunk
  switchport trunk allowed vlan 2217-2218,2398
  channel-group 8 mode active
  no shutdown

interface Ethernet1/56
  description ***PTX-et-0/0/65***
  switchport
  switchport mode trunk
  no shutdown

interface Ethernet1/57

interface Ethernet1/58

interface Ethernet1/59

interface Ethernet1/60

interface Ethernet1/61

interface Ethernet1/62

interface Ethernet1/63

interface Ethernet1/64

interface Ethernet1/65

interface Ethernet1/66

interface mgmt0
  vrf member management
line console
line vty
boot nxos bootflash:/nxos.9.3.11.bin



Upstream-Core-SW#
