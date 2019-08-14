# Graylog-OPNsense_Extractors
Extractors for Graylog to parse OPNsense firewall logs. Should be able to parse most all IPv4 and IPv6 message.
8/13/19 Update to support OPNsense message format change.
6/21/18 Update to IPv6 ICMP. OPNsense sends "ICMPv6", remove case insensitive regex for better processing when under heavy load.
