# SecureRoute: Cisco IOS Initial Router Configuration Lab

Simulated enterprise router hardening and configuration using Cisco Packet Tracer — focused on access control, CLI security, and configuration persistence.

---

## Network Topology

```
  +-------------+          Console Cable (RS-232)          +-------------------------+
  |     PCA     | =======================================> |        Router R1        |
  |  RS-232     |                                          |  CON | Fa0/0 | Fa0/1   |
  |  Terminal   |                                          |      | Gi0/0 | Gi0/1   |
  +-------------+                                          +-------------------------+
                                                                  |         |
                                                           [Fa0/0]          [Gi0/0]
                                                           FastEthernet      GigabitEthernet
                                                           [Fa0/1]          [Gi0/1]
                                                           FastEthernet      GigabitEthernet
```

> PCA connects to R1 via RS-232 console cable. The router exposes 2 FastEthernet and 2 GigabitEthernet interfaces for network connectivity.

---

## Project Overview

This project demonstrates the end-to-end process of securing and configuring a Cisco IOS router from its default state to a hardened, production-ready baseline. Using Cisco Packet Tracer, I verified default settings, applied encrypted password policies, configured security banners, and saved the running configuration — following real-world IT and network administration best practices.

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Cisco Packet Tracer** | Network simulation environment used to safely model router configuration without physical hardware |
| **Cisco IOS CLI** | Command-line interface used to execute privileged EXEC and global configuration commands |
| **RS-232 Console Cable (simulated)** | Established the initial out-of-band console connection to the router (R1) |
| **Enable / Global Config Mode** | Used to escalate privileges and apply system-wide configuration changes |
| **`show running-config`** | Verified live router state including interfaces, hostname, and active settings |

> **Why Packet Tracer?** It mirrors real Cisco IOS behavior without requiring physical hardware, making it the industry-standard simulation tool used in CCNA certification training and IT support environments.

---

## STAR Method

### Situation

Enterprise networks are frequently exposed to unauthorized access due to routers being deployed with default, unsecured configurations — no passwords, no access restrictions, and no warning banners. This is one of the most common vulnerabilities in small-to-mid-size business networks.

### Task

Configure a Cisco router (R1) from its default state to a secure baseline by:

- Verifying the default configuration and interface inventory
- Applying encrypted and plain-text password protection to privileged EXEC and console access
- Configuring a Message of the Day (MOTD) banner to deter unauthorized access
- Saving the running configuration to NVRAM to ensure persistence across reboots

### Action

- Established a console connection from PCA to R1 via RS-232 and accessed the terminal
- Entered privileged EXEC mode using the `enable` command and ran `show running-config` to audit the default state
- Identified the router hostname, 2 FastEthernet interfaces, and 2 GigabitEthernet interfaces
- Applied `enable secret` for encrypted privileged access and `line console 0` password for console port security
- Configured a MOTD banner with an unauthorized access warning
- Ran `copy running-config startup-config` to persist all changes to NVRAM

**Key commands used:**

```
Router> enable
Router# show running-config
Router# configure terminal
Router(config)# hostname R1
Router(config)# enable secret <password>
Router(config)# line console 0
Router(config-line)# password <password>
Router(config-line)# login
Router(config)# banner motd # Unauthorized access is prohibited #
Router# copy running-config startup-config
```

### Result

- Successfully transitioned router from an open, default state to a secured, access-controlled configuration
- Demonstrated ability to audit, configure, and validate Cisco IOS devices — core competencies for Help Desk, IT Support, and Data Center Technician roles
- Completed all 3 lab objectives: verify defaults, configure security, save configuration

---

## Business Impact

| Impact Area | Detail |
|-------------|--------|
| **Security Risk Reduction** | Eliminates default-credential vulnerabilities that account for ~34% of network breaches (Verizon DBIR) |
| **Downtime Prevention** | Unsaved configs cause full reconfiguration after power loss — saving to NVRAM prevents hours of recovery time |
| **Cost Avoidance** | A misconfigured router in an enterprise can cost $5,600/min in downtime (Gartner) — proper baseline configs mitigate this risk |
| **Compliance Alignment** | MOTD banners and access controls align with NIST SP 800-53 and CIS Cisco IOS Benchmark security standards |
| **Operational Readiness** | Skills directly map to Tier 1/Tier 2 IT support, NOC technician, and data center operations roles |

---

## Key Skills Demonstrated

- Cisco IOS CLI navigation (User EXEC → Privileged EXEC → Global Config)
- Network device auditing with `show` commands
- Password encryption and console access hardening
- MOTD banner configuration for legal and security compliance
- Configuration persistence with `copy run start`
- Network topology understanding (FastEthernet vs GigabitEthernet interfaces)

---

## Lab Objectives

- [x] Part 1: Verify the Default Router Configuration
- [x] Part 2: Configure and Verify the Initial Router Configuration
- [x] Part 3: Save the Running Configuration File

---

## Context

This lab was completed as part of my Information Systems degree coursework and Cisco networking studies, aligned with CCNA (200-301) curriculum objectives. It reflects hands-on technical skills applicable to:

- IT Help Desk / Tier 1 Support
- Data Center Technician
- Network Operations Center (NOC)
- Entry-Level Systems Administrator

---

## Contact

**[Your Name]**  
[LinkedIn]([https://linkedin.com/in/yourprofile](https://www.linkedin.com/in/anthony-akor/)) | [GitHub]([https://github.com/yourusername](https://github.com/aakorGithub)) | anthonyakor@yahoo.com
