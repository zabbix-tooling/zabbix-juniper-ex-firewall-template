
Juniper EX Series
-------------------

This template is for the monitoring of Juniper EX series switching hardware via SNMP.

Its based on: https://share.zabbix.com/network_devices/juniper/juniper-ex-series

Advantages:
- host Screens with graph prototypes
- configurable snmp community (macro)
- 64 bit traffic counters
- improved history/trend settings
- monitoring of desired and current interface state<BR>
  (AdminStatus == 1 && OperStatus <> 1)

It requires no additional files or components - just add the template and you're done.

Monitors the following items:

* Device availability (ping check)
* Alarm status (red / yellow)
* 5 minute load average
* CPU use
* Memory use
 * Routing engine temperature
 * Interfaces
		* Inbound discarded packets
		* Inbound errors
		* Inbound traffic
		* Outbound discarded packets
		* Outbound errors
		* Outbound traffic

Discovery will detect your ports and VLANs, and this will work in virtual chassis configurations.

Tested with the following hardware:

* EX4600
* EX3300
* EX2200

All suggestions, mergerequests, ideas and contributors are welcome!

How to use it
--------------

  * Configure a SNMPv2 community on the switch
  * Disable all unused ports on the switch to get AdminStatus != 1
  * Create zabbix switch with a snmp interface
  * Configure the {$SNMP_COMMUNITY} macro

Enhance it
----------

Use the mibs at https://www.juniper.net/documentation/en_US/release-independent/junos/mibs/mibs.html

- fork this project
- always use numeric oids
- create pull request
