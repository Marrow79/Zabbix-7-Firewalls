# Zabbix 7 Firewall SNMP Template Pack — Canada

Generated: 2026-09-28
Model-specific templates: 511
Manufacturer/product families: 14
Zabbix export version: 7.0

## Contents

- One Zabbix 7 YAML template per firewall model under `templates/<vendor>/`.
- `all_firewalls_combined_zabbix_7_snmp.yaml` for a single bulk import.
- `manifest.csv` and `manifest.json` mapping every model to its source documentation.
- `VALIDATION.txt` containing structural validation results.
- `SHA256SUMS.txt` for integrity checking.

## Monitoring included

Every template includes ICMP reachability, SNMPv2-MIB system identity/uptime, IF-MIB interface discovery, administrative and operational status, interface speed, 64-bit traffic counters, errors/discards, an unreachable-firewall trigger, interface-down trigger prototypes, and traffic/error graph prototypes. Numeric OIDs are used so local MIB text files are not required.

No SNMP community strings or SNMPv3 credentials are embedded. Configure credentials on the Zabbix host SNMP interface. SNMPv3 is preferred where supported.

## Scope

There is no single authoritative registry of every firewall sold through every Canadian reseller, and vendor model availability changes. This pack is a broad 2026-09-28 research pass over major dedicated firewall/security-gateway manufacturers with public product documentation and SNMP support documentation. The source URLs used for inclusion are recorded in the manifest and below.

SNMP support is often documented at the firewall operating-system or appliance-family level rather than repeated on every SKU page. A model is included when it is in the researched vendor model family and that firewall family/OS documents SNMP monitoring.

The baseline deliberately avoids guessed proprietary OIDs. For model-specific CPU, memory, VPN, HA, session, temperature, fan/PSU, security-engine, or license metrics, extend a template only after verifying the vendor MIB against the exact firmware release.

## Vendor/model counts

- Fortinet: 136
- Palo Alto Networks: 53
- Cisco Secure Firewall: 37
- Cisco Meraki: 15
- Sophos: 31
- SonicWall: 40
- WatchGuard: 39
- Juniper: 18
- Check Point: 30
- Barracuda: 34
- Zyxel: 23
- Netgate: 11
- Stormshield: 17
- Forcepoint: 27

## Import

1. In Zabbix 7, open **Data collection > Templates > Import**.
2. Import either the combined YAML or the individual model YAML files you need.
3. On each firewall host, add/configure an SNMP interface and its credentials.
4. Enable SNMP on the firewall and permit polling from the Zabbix server or proxy IP.
5. Link the matching model template.

## Research sources

### Fortinet
- https://docs.fortinet.com/document/fortigate/latest/fortios-release-notes/760203/introduction-and-supported-models
- https://docs.fortinet.com/document/fortigate/7.6.4/fortios-release-notes/760203/introduction-and-supported-models
- Note: Enable/configure the FortiGate SNMP agent and allow SNMP on the monitored management interface.

### Palo Alto Networks
- https://docs.paloaltonetworks.com/hardware
- https://docs.paloaltonetworks.com/pan-os/11-1/pan-os-admin/monitoring/snmp-monitoring-and-traps/snmp-support

### Cisco Secure Firewall
- https://www.cisco.com/site/ca/en/products/security/firewalls/index.html
- https://www.cisco.com/c/en/us/td/docs/security/secure-firewall/mib/cisco-secure-firewall-mib-reference-guide.html

### Cisco Meraki
- https://meraki.cisco.com/products/appliances/z1
- https://documentation.meraki.com/General_Administration/Monitoring_and_Reporting/SNMP_Overview_and_Configuration
- Note: Meraki SNMP is normally exposed through the Meraki Dashboard/cloud SNMP service rather than a conventional device-local SNMP agent. Validate the host/interface design in Zabbix before deployment.

### Sophos
- https://docs.sophos.com/nsg/sophos-firewall/22.0/Help/en-us/webhelp/onlinehelp/
- https://docs.sophos.com/nsg/sophos-firewall/21.0/Help/en-us/webhelp/onlinehelp/AdministratorHelp/Administration/SNMP/index.html
- Note: Enable the SNMP agent and allow SNMP device access from the monitoring zone.

### SonicWall
- https://www.sonicwall.com/support/technical-documentation/docs/sonicos8-device-settings/Content/SNMP/group-creating.htm
- https://www.sonicwall.com/es-mx/support/knowledge-base/sonicwall-gen8-tzs-and-gen8-nsas-settings-migration/kA1VN0000000RrR0AU
- https://www.sonicwall.com/support/technical-documentation/docs/sonicos-7-0-0-0-release_notes/Content/Versions/sonicos-7-0-1-13-5161.htm
- Note: SonicOS SNMP is disabled by default. Enable SNMP and permit SNMP management on the appropriate interface/zone.

### WatchGuard
- https://www.watchguard.com/help/docs/help-center/en-US/Content/en-US/Hardware-Guides/intro/firebox-hardware-guides.html
- https://www.watchguard.com/help/docs/help-center/en-US/Content/en-US/Fireware/system_status/snmp_about_c.html

### Juniper
- https://www.juniper.net/documentation/us/en/software/jsi/juniper-support-insights-user-guide/jsi-jcloud-user-guide/topics/concept/jsi-supported-devices.html
- https://www.juniper.net/documentation/us/en/software/junos/network-mgmt/topics/topic-map/snmp-mibs-supported-by-junos-os-and-junos-os-evolved.html

### Check Point
- https://www.checkpoint.com/products/security-gateway-appliances/
- https://www.checkpoint.com/quantum/next-generation-firewall/small-business-firewall/
- https://sc1.checkpoint.com/documents/R81.10/WebAdminGuides/EN/CP_R81.10_Gaia_AdminGuide/Topics-GAG/SNMP.htm
- Note: Gaia SNMP is disabled by default. Enable it and prefer SNMPv3 where supported.

### Barracuda
- https://documentation.campus.barracuda.com/wiki/spaces/NGFEOL/pages/756187195

### Zyxel
- https://www.zyxel.com/us/en-us/products/firewall-ngfw
- https://community.zyxel.com/en/discussion/18671/nebula-firewall-matrix-table-zld5-41-uos1-36

### Netgate
- https://docs.netgate.com/pfsense/en/latest/product-manuals.html
- https://docs.netgate.com/pfsense/en/latest/services/snmp.html
- Note: pfSense Plus provides SNMP through its SNMP service (bsnmpd). Enable Services > SNMP on the firewall.

### Stormshield
- https://www.stormshield.com/products-services/products/network-security/product-range-sns/
- https://documentation.stormshield.com/PLC/SNS/en/Content/PDF/sns-en-product_lifecycle_guide.pdf

### Forcepoint
- https://help.forcepoint.com/ngfw/en-us/7.0.3/releasenotes/ngfw/GUID-EB85790B-C83A-499C-B634-4CD5B0BEE720.html
- https://help.forcepoint.com/ngfw/en-us/7.0.0/GUID-6D0B949F-CA4E-4EEF-BAB4-AF7C248D9EB7.html
- Note: Forcepoint NGFW SNMP support is version-dependent. NGFW 7.0 provides an enhanced SNMP agent and proprietary FORCEPOINT-NGFW-ENGINE-MIB objects.

## Validation

All model YAML files and the combined YAML were parsed with PyYAML/libyaml. The validator checked Zabbix export version 7.0, model/template counts, required baseline items, interface discovery, item prototypes, graph prototypes, UUID format and UUID uniqueness across the combined template set.

A live Zabbix frontend/API import was not available in this execution environment; therefore this is structural/export-format validation, not a live-server import certification.
