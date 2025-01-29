# Graylog-OPNsense_Extractors
Extractors for Graylog to parse OPNsense firewall logs. Should be able to parse most all IPv4/IPv6, ICMP, UDP, & TCP messages.


## Versions
In the past I maintained two versions of the extractors, depending on how you have the OPNsense logging destination configured. OPNsense is capable of sending either RFC 5424-compliant logs or more basic syslog messages. The RFC log messages are generally preferred, as they include timezone information (instead of simply sending a bare timestamp in the local system timezone, which Graylog may misintrepret). I currently only maintain the RFC5424 format.

Current build based on:
OPNsense 24.7.12_2

Graylog 5.0.13+083613e, codename Noir

## Usage
1. Open Graylog as admin
2. Open 'System / Inputs', click on 'Inputs'
3. Select the input you forward OPNsense filterlog to. Click "More actions' > "Edit input", and ensure "Store full message?" is enabled.
4. For the input OPNsense is forwarding into, click on "Manage extractors"
5. Drop down "Actions" in the top right corner, then click "Import extractors"
6. Paste the contents of the desired JSON file into the box. Click "Add extractors to input"

#
## Update notes
6/21/18 Update to IPv6 ICMP. OPNsense sends "ICMPv6", remove case insensitive regex for better processing when under heavy load.
#
8/13/19 Update to support OPNsense message format change.
#
6/26/21 Update - Removed some ICMP extractors. Updated to new OPNsense log message format.
#
12/2/21 Update - Fixed incorrect CSV headers. Removed OPNsense-Unbound_Extractor. 
#
12/31/23 Update - Modified the regex to accomodate the 'meta sequenceID' tags
#
1/27/25 Update - Added IGMP extractors. Thank you github.com/drheat for your contribution.
#
1/29/25 - Update - Standardized order and some field names. Added IP extractors.

