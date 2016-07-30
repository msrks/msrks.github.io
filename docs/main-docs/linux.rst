========================================
Atom
========================================
.. highlight:: bash

各種設定

基本設定
-----------
ip設定::

  $ sudo ifconfig eth0 inet 10.0.0.100 netmask 255.0.0.0 up
  $ sudo route add default gw 10.0.0.1


SNMP server
------------
netsnmp::

  $ sudo apt-get install snmp sniped
  $ snmpwalk -v 2c -c public <ip-addr> <mib-dir>

DHCP server
--------------
isc-dhcp-server::

  $ sudo apt-get install isc-dhcp-server
  $ sudo leafpad /etc/dhcp/dhcp.conf
      # dhcp-relayを動作させるためには自ネットワークと、アドレス付与ネットワークの両方について設定を記述する必要がある
      subnet 172.16.0.0 netmask 255.255.255.0 {}
      subnet 192.168.0.0 netmask 255.255.255.0 {
        range 192.168.0.2 192.168.0.250;
        option routers 192.168.0.1;
        option subnet-mask 255.255.255.0
        # dns setting
        #
        #
      }
  $ sudo leafpad /etc/default/isc-dhcp-server
      # INTERFACE = "eth0" を追加
  $ sudo touch /var/lib/dhcp/dhcpd.leases
  $ sudo systemctl stop isc-dhcp-server.service
  $ sudo systemctl start isc-dhcp-server.service
  $ sudo systemctl enable isc-dhcp-server.service

Packet Capture
-----------------
wireshark::

  $ sudo apt-get install wireshark
  $ sudo groupadd wireshark
  $ sudo usermod -a -G wireshark pi
  $ sudo chgrp wireshark /usr/bin/dumpcap
  $ sudo chmod 750 /usr/bin/dumpcap
  $ sudo raspi-config
  $ sudo setcap cap_net_raw.cap_net_admin=eip /usr/bin/dumpcap
  $ sudo chmod 4711 'which dumpcap'
  $ sudo chmod 4711 /usr/bin/dumpcap
