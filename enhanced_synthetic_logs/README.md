# Enhanced Synthetic Logs for Threat Hunting

This directory contains enhanced synthetic security logs designed for testing and developing threat hunting capabilities in the Human-in-the-Loop Threat Hunting Orchestrator.

## Overview

These logs represent realistic attack scenarios with the following enhancements:

- **Correlation IDs**: Link related events across different log types
- **Realistic Threat Scenarios**: Based on actual attack patterns and techniques
- **Geographic Diversity**: Logs from multiple countries and regions
- **Multiple Threat Types**: Ransomware, data exfiltration, phishing, lateral movement, and more
- **Temporal Progression**: Events that follow realistic attack timelines

## Threat Scenarios

### 1. Ransomware Attack Scenario (`ransomware_attack_scenario.json`)

**Attack Pattern**: WannaCry-style ransomware with SMB exploitation
- **Correlation ID**: `ransomware-attack-2024-12-15-001`
- **Geographic Origin**: Russia (Moscow)
- **Log Types**: SecurityAlert, SecurityEvent, CommonSecurityLog, AppServiceHttpLogs, DNSEvents
- **Key Indicators**:
  - PowerShell execution with bypass
  - SMB exploitation attempts
  - DNS queries to killswitch domains
  - File encryption activities

### 2. Data Exfiltration Scenario (`data_exfiltration_scenario.json`)

**Attack Pattern**: Credential theft followed by lateral movement and data theft
- **Correlation ID**: `data-exfiltration-2024-12-16-001`
- **Geographic Origin**: United States (New York)
- **Log Types**: SecurityAlert, SigninLogs, SecurityEvent, CommonSecurityLog, AuditLogs
- **Key Indicators**:
  - Suspicious sign-in from external location
  - Lateral movement between systems
  - Large data transfers to external IPs
  - Privilege escalation attempts

### 3. Phishing Campaign Scenario (`phishing_campaign_scenario.json`)

**Attack Pattern**: Multi-stage phishing with credential harvesting and malware delivery
- **Correlation ID**: `phishing-campaign-2024-12-17-001`
- **Geographic Origins**: Russia, United Kingdom
- **Log Types**: EmailEvents, EmailAttachmentInfo, EmailUrlInfo, AppServiceHttpLogs, SigninLogs, SecurityEvent, DNSEvents, CommonSecurityLog, SecurityAlert
- **Key Indicators**:
  - Suspicious email delivery
  - Credential harvesting attempts
  - PowerShell download activities
  - C2 communication attempts

### 4. Global Threat Scenario (`global_threat_scenario.json`)

**Attack Pattern**: Coordinated attacks from multiple nation-state actors
- **Correlation ID**: `global-attack-campaign-2024-12-18-001`
- **Geographic Origins**: Russia, China, North Korea, Iran
- **Log Types**: SecurityAlert, CommonSecurityLog, SigninLogs, DNSEvents, AppServiceHttpLogs, SecurityEvent
- **Key Indicators**:
  - DDoS attacks from Russian IPs
  - Credential harvesting from Chinese IPs
  - SQL injection from North Korean IPs
  - APT activity from Iranian IPs

## Log Types Included

### Security Alerts
- Microsoft Defender ATP alerts
- Various threat types and severity levels
- Detailed entity information
- MITRE ATT&CK tactics mapping

### Authentication Events
- SigninLogs with geographic location data
- Failed and successful authentication attempts
- Device and browser information
- Risk-based authentication events

### Security Events
- Windows Security Event logs
- Process creation events (4688)
- Logon events (4624, 4625)
- Detailed command line information

### Network Security
- CommonSecurityLog from various vendors
- Palo Alto Networks, Cisco, Fortinet, Check Point
- Geographic location data
- Threat categorization

### Email Security
- EmailEvents with threat detection
- EmailAttachmentInfo with file analysis
- EmailUrlInfo with URL reputation
- Phishing and malware indicators

### DNS Events
- DNS query logs
- Malicious domain lookups
- C2 communication patterns
- Geographic distribution

### Application Logs
- AppServiceHttpLogs
- Web application attacks
- API abuse patterns
- Authentication bypass attempts

### Audit Logs
- Administrative activities
- Privilege escalation
- User management changes
- Resource access patterns

## Geographic Diversity

The logs include events from various geographic locations:

- **Russia**: Moscow (55.7558, 37.6176)
- **China**: Beijing (39.9042, 116.4074)
- **North Korea**: Pyongyang (39.0194, 125.7381)
- **Iran**: Tehran (35.6892, 51.3890)
- **United States**: New York (40.7128, -74.0060)
- **United Kingdom**: London (51.5074, -0.1278)

## Threat Types Covered

1. **Ransomware**: File encryption, killswitch domains, SMB exploitation
2. **Data Exfiltration**: Large data transfers, credential theft, lateral movement
3. **Phishing**: Email-based attacks, credential harvesting, malware delivery
4. **DDoS**: Distributed denial of service attacks
5. **SQL Injection**: Database attacks and exploitation
6. **Advanced Persistent Threat (APT)**: Sophisticated nation-state attacks
7. **Command and Control (C2)**: Malware communication patterns
8. **Lateral Movement**: Network traversal and privilege escalation

## Usage

These logs can be used for:

- **Threat Hunting Training**: Practice identifying attack patterns
- **Detection Development**: Test and validate security rules
- **Incident Response**: Simulate realistic incident scenarios
- **Security Tool Testing**: Validate SIEM and security analytics platforms
- **Research and Development**: Develop new security capabilities

## Correlation IDs

Each scenario uses a unique correlation ID that links all related events:

- `ransomware-attack-2024-12-15-001`
- `data-exfiltration-2024-12-16-001`
- `phishing-campaign-2024-12-17-001`
- `global-attack-campaign-2024-12-18-001`

This allows for easy tracking of attack progression across different log sources and time periods.

## Data Schema

All logs follow Azure Sentinel's ASIM (Azure Sentinel Information Model) schema, ensuring compatibility with:

- Azure Sentinel
- Microsoft 365 Defender
- Microsoft Defender ATP
- Other SIEM platforms

## Contributing

When adding new scenarios:

1. Use realistic attack patterns
2. Include correlation IDs
3. Add geographic diversity
4. Follow ASIM schema standards
5. Include multiple log types
6. Provide temporal progression

## Security Note

These are synthetic logs for testing purposes only. They do not contain real sensitive data or actual attack information. 