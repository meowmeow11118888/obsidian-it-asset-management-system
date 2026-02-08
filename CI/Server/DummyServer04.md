---
ci-type: Server
division: "[[IT]]"
department: "[[Infra]]"
name: DummyServer03
description: Production web server for dummy application hosting
service-tag: SRV-TAG-001
property-no: PROP-2026-001
asset-tag: ASSET-SRV-001
processor-name: Intel Xeon E5-2680 v4
processor-count: 2
core-per-cpu: 14
memory-gb: 64
disk-gb: 1000
manufacturer: Dell
serial-number: SN-DELL-20260101
hardware-device-name: Dell PowerEdge R740
network-card-count: 2
on-board-nic-count: 4
fiber-card-count: 0
fiber-port:
network-port-count: 4
ip-address: 192.168.1.104
mac-address: 00:1A:2B:3C:4D:5E
virtual-ip: 192.168.1.200
kvm-ip: 192.168.100.50
backup-lan-ip: 10.0.1.100
heartbeat-ip: 172.16.1.100
external-ip:
operating-system: Ubuntu Server
os-details: Ubuntu 22.04.3 LTS
service-pack: Kernel 5.15.0-91
unsupported-software:
location: Taipei Data Center - Floor 3
environment: Production
data-center: TPE-DC-01
rack-no: Rack-A-15
switch-name: SW-CORE-01
switch-port: Gi1/0/24
region-tag: APAC-TW
primary-admin: "[[Huang]]"
proxy-admin: "[[Lin]]"
property-owner: IT Department
support-team: Infrastructure Support Team
entity-scope: Taiwan Entity
server-status: Active
power-on-off: On
auto-reboot-after-patch: Yes
golden-key: GK-2026-001
internet-facing: No
est-retire-upgrade-date: 2029-12-31
last-checked-time: 2026-02-07
cloud-account:
linked-instance:
type: Physical
wwn:
hosts-application:
  - "[[DummyApp02]]"
member-of-cluster: []
runs-service-function: []
---

