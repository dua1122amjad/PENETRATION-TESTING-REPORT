# PENETRATION-TESTING-REPORT
## FOOTPRINTING & NETWORK SCANNING
**Week 2 • Cybersecurity / Ethical Hacking Practical**

---

## 📋 Report Details

| Report Field | Details |
| :--- | :--- |
| **Analyst** | Cybersecurity Trainee |
| **Practical Focus** | Footprinting & reconnaissance, network discovery |
| **Primary Platforms** | Kali Linux and Windows |
| **Tools Covered** | WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, DNSRecon, Zenmap |
| **Assessment Scope** | Authorized educational lab / controlled environment |
| **Sanitization** | Live IPs, domains, emails and other identifiers replaced with documentation-safe values |
| **Report Status** | Sanitized submission-ready draft |

> 🔒 **Authorization & Safety Notice:**  
> All reconnaissance and scanning activities described in this report are presented as authorized educational exercises. The report intentionally uses documentation-only IP ranges and synthetic identifiers so that the final document does not expose live infrastructure details. Prepared for educational and portfolio use.

---

## 1. Executive Summary

This practical exercise covered two complementary cybersecurity activities: passive and low-impact footprinting of a web-domain environment (`W2-PM1`), followed by local network discovery with Zenmap (`W2-PM5`). The work demonstrated how a security professional can move from publicly observable information to a structured view of hosts and services without attempting exploitation.

The uploaded practical evidence showed the use of WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon for reconnaissance, and Zenmap/Nmap for host discovery. This report documents what each tool contributes to the overall security analysis.

### Key Outcomes

| Area | Outcome |
| :--- | :--- |
| **Domain Footprinting** | Collected registration, DNS, web-technology, HTTP-header and WAF observations using 6 Kali tools. |
| **Network Discovery** | Used Zenmap/Nmap to identify an active host and observe exposed TCP services in the lab. |
| **Risk Interpretation** | Converted observations into potential risks without claiming that an observation is automatically a vulnerability. |
| **Data Protection** | Replaced live IPs and identifying values with safe documentation ranges/placeholders. |

---

## 2. Objectives

- Understand the purpose of footprinting before active security testing.
- Practice common Kali Linux reconnaissance commands and interpret their outputs (`W2-PM1`).
- Use Zenmap to discover live hosts and visible services on an authorized lab network (`W2-PM5`).
- Document evidence, security implications and recommendations in a professional report (`W2-PM-FINAL`).
- Produce a sanitized report that does not reproduce live IP addresses or sensitive identifiers.

---

## 3. Scope, Authorization & Methodology

The activities are framed as an authorized educational lab. Testing was strictly limited to systems where permission was secured.

| Phase | Module | Activity | Primary Tools | Evidence Type |
| :--- | :--- | :--- | :--- | :--- |
| **Phase 1** | W2-PM1 | Footprinting / Reconnaissance | WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, DNSRecon | Terminal outputs |
| **Phase 2** | W2-PM5 | Network Discovery | ipconfig, Zenmap/Nmap | Scan output / topology |
| **Phase 3** | W2-PM-FINAL | Risk Interpretation | Manual analysis | Risk register |
| **Phase 4** | W2-PM-FINAL | Recommendations | Manual analysis | Mitigation guidance |

### Sanitization Standard
To reduce the possibility of accidental data exposure, this report does not reproduce live IP addresses, domain identifiers, or registrar values. External example IPs use documentation ranges such as `192.0.2.0/24`. Internal examples are presented as synthetic values.

> 💡 **Important:** Sanitized values are placeholders for documentation and do not reflect real-world target systems.

---

## 4. Tools Used

| Tool | Module | Purpose in the Practical |
| :--- | :--- | :--- |
| **Kali Linux** | Platform | Operating environment for reconnaissance commands. |
| **WHOIS** | W2-PM1 | Review publicly available domain-registration information and name servers. |
| **WhatWeb** | W2-PM1 | Fingerprint web technologies and server/application indicators. |
| **Nslookup** | W2-PM1 | Resolve a domain name through DNS. |
| **Curl -I** | W2-PM1 | Inspect HTTP response headers. |
| **Wafw00f** | W2-PM1 | Identify whether a web application firewall is detectable. |
| **DNSRecon** | W2-PM1 | Enumerate DNS record types and related infrastructure information. |
| **Zenmap / Nmap** | W2-PM5 | Discover live hosts and identify visible TCP services in an authorized network. |
| **Windows ipconfig** | W2-PM5 | Identify local host IP configuration and subnet before scanning. |

---

## 5. Module W2-PM1: Footprinting & Reconnaissance

The footprinting phase utilized 6 core Kali Linux tools to combine registration data, DNS information, web fingerprints, HTTP metadata, and WAF detection.

### 5.1 WHOIS
**Objective:** Identify publicly available domain-registration information and authoritative name servers.

```bash
whois example-lab.invalid
```
- **Sanitized Observation:** Demonstrated that WHOIS exposes registrar details, domain status, and name-server configurations.
- **Security Relevance:** Provides structural and administrative context regarding target domain ownership.
### 5.2 WhatWeb
**Objective:** Fingerprint web technologies exposed by the target web application.

```bash
whatweb example-lab.invalid
```
- **Sanitized Observation:** Identified web server components, CMS frameworks, download handlers, and JavaScript libraries.
- **Security Relevance:** Technology identification assists in prioritizing software update requirements and defensive patch management.
