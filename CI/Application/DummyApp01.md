---
ci-type: Application
division: "[[IT]]"
department: "[[Infra]]"
name: DummyApp01
description: Dummy web application for customer portal services
status: Active
category: Web Application
entity: Taiwan Branch
location: Taipei Data Center - Floor 3
environment: Production
external-endpoint: https://dummy.example.com
external-fqdn: dummy.example.com
internal-endpoint: http://dummyapp01.internal.local
internal-fqdn: dummyapp01.internal.local
internal-ip: 192.168.1.100
external-ip: 203.0.0.0
scan-ip: 192.168.1.100
instance-ip: 192.168.1.100
ssl: Yes
security-assessment: Completed
security-certification: ISO 27001
pii-data: Yes
pii-application-encryption: AES-256
pii-encryption-completion-date: 2025-12-01
other-confidential-data: Customer transaction records
hosting-type: On-Premise
license-key: DUMMY-APP-LICENSE-2026
installation-path: /opt/dummyapp01
date-installed-on: 2025-11-15
code-available: Yes
primary-admin: "[[Lin]]"
proxy-admin: "[[Lin]]"
last-business-continuity-drill-date: 2025-12-20
next-business-continuity-drill-eta: 2026-06-20
outsourcing-type: In-house Development
contract: N/A
hosted-on-server:
  - "[[CI/Server/DummyServer01]]"
  - "[[CI/Server/DummyServer02]]"
  - "[[CI/Server/DummyServer03]]"
part-of-cluster: []
uses-repository: []
secured-by-certificate: []
scanned-by-sast: []
runs-service: "[[CI/Service/DummyService01]]"
---
