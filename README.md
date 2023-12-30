# Graylog-OPNsense_Extractors
Extractors for Graylog to parse OPNsense firewall logs. Should be able to parse most all IPv4/IPv6, ICMP, UDP, & TCP messages.

# Graylog Changes
Graylog has changed the way extractors are implemented, instructions below may not be accurate for newer versions of Graylog.

## Versions
There are two versions of the extractors, depending on how you have the OPNsense logging destination configured. OPNsense is capable of sending either RFC 5424-compliant logs or more basic syslog messages. The RFC log messages are generally preferred, as they include timezone information (instead of simply sending a bare timestamp in the local system timezone, which Graylog may misintrepret).

The extractors for the two versions are similar, but because Graylog will strip some data from the message as it parses the RFC logs, we must include the full message for the extractor to parse, as detailed below.

## Usage
1. Open Graylog. Navigate to the input you wish to run the extractor on.
2. Click on "Manage extractors". 
3. Drop down "Actions" in the top right corner, then click "Import extractors"
4. Paste the contents of the desired JSON file into the box. Click "Add extractors to input"
5. **If using RFC 5424 logs**: Navigate back to the input, click "More actions' > "Edit input", and ensure "Store full message?" is enabled.
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
12/29/23 Update - Modified the regex for RFC 5424 messages



