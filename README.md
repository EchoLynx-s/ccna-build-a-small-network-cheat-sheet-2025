# CCNA – Build a Small Network (Module 17)

Quick-reference notes for NetAcad CCNA – **Module 17: Build a Small Network**.  
Focus is on taking everything from previous modules (IP, switching, routing, security)
and using it to **design, build, verify, and troubleshoot a small business network**.

I use this repo to revise:

- Typical **small network topologies** and how to pick the right **devices**.
- How to **plan IP addressing, redundancy, and basic traffic management** (QoS-ish).
- Which **applications and protocols** are common in small business networks.
- How to **verify connectivity** with ping / traceroute and build a **baseline**.
- Core **host & IOS commands** (`ipconfig`, `ifconfig`, `show ip interface brief`, `show cdp neighbors`, etc.).
- Structured **troubleshooting methodologies** and classic **small-network issues** (duplex, IP, DNS, default gateway).
- End-of-course style **integration labs**: design, build, and troubleshoot a full small network.

---

## Table of Contents

- [Module 17 Overview](#module-17-overview)  
- [Module Map](#module-map)  

- [17.0 Introduction](#170-introduction)  
  - [17.0.1 Why should I take this module?](#1701-why-should-i-take-this-module)  
  - [17.0.2 What will I learn to do in this module?](#1702-what-will-i-learn-to-do-in-this-module)  

- [17.1 Devices in a Small Network](#171-devices-in-a-small-network)  
  - [17.1.1 Small Network Topologies](#1711-small-network-topologies)  
  - [17.1.2 Device Selection for a Small Network](#1712-device-selection-for-a-small-network)  
  - [17.1.3 IP Addressing for a Small Network](#1713-ip-addressing-for-a-small-network)  
  - [17.1.4 Redundancy in a Small Network](#1714-redundancy-in-a-small-network)  
  - [17.1.5 Traffic Management](#1715-traffic-management)  
  - [17.1.6 Check Your Understanding – Devices in a Small Network](#1716-check-your-understanding--devices-in-a-small-network)  

- [17.2 Small Network Applications and Protocols](#172-small-network-applications-and-protocols)  
  - [17.2.1 Common Applications](#1721-common-applications)  
  - [17.2.2 Common Protocols](#1722-common-protocols)  
  - [17.2.3 Voice and Video Applications](#1723-voice-and-video-applications)  
  - [17.2.4 Check Your Understanding – Small Network Applications and Protocols](#1724-check-your-understanding--small-network-applications-and-protocols)  

- [17.3 Scale to Larger Networks](#173-scale-to-larger-networks)  
  - [17.3.1 Small Network Growth](#1731-small-network-growth)  
  - [17.3.2 Protocol Analysis](#1732-protocol-analysis)  
  - [17.3.3 Employee Network Utilization](#1733-employee-network-utilization)  
  - [17.3.4 Check Your Understanding – Scale to Larger Networks](#1734-check-your-understanding--scale-to-larger-networks)  

- [17.4 Verify Connectivity](#174-verify-connectivity)  
  - [17.4.1 Verify Connectivity with Ping](#1741-verify-connectivity-with-ping)  
  - [17.4.2 Extended Ping](#1742-extended-ping)  
  - [17.4.3 Verify Connectivity with Traceroute](#1743-verify-connectivity-with-traceroute)  
  - [17.4.4 Extended Traceroute](#1744-extended-traceroute)  
  - [17.4.5 Network Baseline](#1745-network-baseline)  
  - [17.4.6 Lab – Test Network Latency with Ping and Traceroute](#1746-lab--test-network-latency-with-ping-and-traceroute)  

- [17.5 Host and IOS Commands](#175-host-and-ios-commands)  
  - [17.5.1 IP Configuration on a Windows Host](#1751-ip-configuration-on-a-windows-host)  
  - [17.5.2 IP Configuration on a Linux Host](#1752-ip-configuration-on-a-linux-host)  
  - [17.5.3 IP Configuration on a macOS Host](#1753-ip-configuration-on-a-macos-host)  
  - [17.5.4 The arp Command](#1754-the-arp-command)  
  - [17.5.5 Common show Commands Revisited](#1755-common-show-commands-revisited)  
  - [17.5.6 The show cdp neighbors Command](#1756-the-show-cdp-neighbors-command)  
  - [17.5.7 The show ip interface brief Command](#1757-the-show-ip-interface-brief-command)  
  - [17.5.8 Video – The show version Command](#1758-video--the-show-version-command)  
  - [17.5.9 Packet Tracer – Interpret show Command Output](#1759-packet-tracer--interpret-show-command-output)  

- [17.6 Troubleshooting Methodologies](#176-troubleshooting-methodologies)  
  - [17.6.1 Basic Troubleshooting Approaches](#1761-basic-troubleshooting-approaches)  
  - [17.6.2 Resolve or Escalate?](#1762-resolve-or-escalate)  
  - [17.6.3 The debug Command](#1763-the-debug-command)  
  - [17.6.4 The terminal monitor Command](#1764-the-terminal-monitor-command)  
  - [17.6.5 Check Your Understanding – Troubleshooting Methodologies](#1765-check-your-understanding--troubleshooting-methodologies)  

- [17.7 Troubleshooting Scenarios](#177-troubleshooting-scenarios)  
  - [17.7.1 Duplex Operation and Mismatch Issues](#1771-duplex-operation-and-mismatch-issues)  
  - [17.7.2 IP Addressing Issues on IOS Devices](#1772-ip-addressing-issues-on-ios-devices)  
  - [17.7.3 IP Addressing Issues on End Devices](#1773-ip-addressing-issues-on-end-devices)  
  - [17.7.4 Default Gateway Issues](#1774-default-gateway-issues)  
  - [17.7.5 Troubleshooting DNS Issues](#1775-troubleshooting-dns-issues)  
  - [17.7.6 Packet Tracer – Troubleshoot Connectivity Issues](#1776-packet-tracer--troubleshoot-connectivity-issues)  
  - [17.7.7 Lab – Troubleshoot Connectivity Issues](#1777-lab--troubleshoot-connectivity-issues)  

- [17.8 Module Practice and Quiz](#178-module-practice-and-quiz)  
  - [17.8.1 Lab – Design and Build a Small Business Network](#1781-lab--design-and-build-a-small-business-network)  
  - [17.8.2 Packet Tracer – Skills Integration Challenge](#1782-packet-tracer--skills-integration-challenge)  
  - [17.8.3 Packet Tracer – Troubleshooting Challenge](#1783-packet-tracer--troubleshooting-challenge)  
  - [17.8.4 What did I learn in this module?](#1784-what-did-i-learn-in-this-module)  
  - [17.8.5 Module Quiz – Build a Small Network](#1785-module-quiz--build-a-small-network)  

---

## Module 17 Overview

> **Goal:** Take all your CCNA basics (switching, routing, IP, security) and apply
> them to **design, build, verify, and troubleshoot** a realistic small-business network:
> from choosing the right devices and IP plan to validating connectivity and fixing issues.

---

## Module Map

| Topic                             | Focus                                                                 |
|-----------------------------------|-----------------------------------------------------------------------|
| 17.1 Devices in a Small Network   | Topologies, device roles, addressing, redundancy, basic QoS/traffic mgmt |
| 17.2 Small Network Apps & Protocols | Common services (web, email, file sharing, VoIP/video) and their protocols |
| 17.3 Scale to Larger Networks     | Growth considerations, protocol analysis, utilisation patterns        |
| 17.4 Verify Connectivity          | Ping/traceroute (basic & extended) + building a latency/baseline view|
| 17.5 Host & IOS Commands          | PC IP config tools + key IOS `show`/`arp`/`cdp` commands              |
| 17.6 Troubleshooting Methodologies| Structured troubleshooting, escalation, using `debug` + `terminal monitor` |
| 17.7 Troubleshooting Scenarios    | Hands-on: duplex, IP, gateway, DNS, connectivity issues               |
| 17.8 Practice and Quiz            | Full small-business design, integration and troubleshooting challenges|

---

# CCNA: Introduction to Networks (ITN) — Module 17
## Part 1 — 17.0 Introduction + 17.1.1–17.1.2 (Build a Small Network)

> **Source note:** This section is paraphrased **only** from the screenshots you provided.

---

## 17.0 Introduction

Module 17 is the final module of the **CCNA: Introduction to Networks (ITN)** course.  
You already have the fundamentals — now the goal is to **apply them to a real small-network build**:
design it, connect it, verify it works, and troubleshoot common issues.

---

## 17.0.1 Why should I take this module?

Welcome to **Build a Small Network**.

This module is essentially a “put it all together” step:
- you **build** a small network,
- you **verify** connectivity and expected operation,
- and you **troubleshoot** typical problems you’ll encounter in the real world.

It includes **labs** and **Packet Tracer activities** to practice the skills a network administrator needs.

---

## 17.0.2 What will I learn to do in this module?

**Module Title:** Build a Small Network  
**Module Objective:** Implement a network design for a small network that includes a **router**, a **switch**, and **end devices**.

### Topic objectives (from the module outline)

| Topic Title | Topic Objective |
|---|---|
| Devices in a Small Network | Identify the devices used in a small network. |
| Small Network Applications and Protocols | Identify the protocols and applications used in a small network. |
| Scale to Larger Networks | Explain how a small network serves as the basis of larger networks. |
| Verify Connectivity | Use the output of **ping** and **tracert** to verify connectivity and establish relative network performance. |
| Host and IOS Commands | Use host and IOS commands to acquire information about the devices in a network. |
| Troubleshooting Methodologies | Describe common network troubleshooting methodologies. |
| Troubleshooting Scenarios | Troubleshoot issues with devices in the network. |

---

## 17.1 Devices in a Small Network

Small networks still require planning. You typically combine:
- a **router** (often the internet edge / default gateway),
- a **switch** (LAN connectivity),
- and possibly a **wireless access point** (wireless users),
plus the end devices your business needs.

---

## 17.1.1 Small Network Topologies

Most businesses are small, so most business networks are also small.

A small network design is usually straightforward because it has fewer devices than a large network.  
A typical small business network can include:
- a router,
- a switch,
- a wireless access point for wired + wireless users,
- end devices like PCs/laptops,
- and shared resources such as an **IP phone**, **printer**, and **server**.

Small networks commonly have **one WAN/Internet connection**, which might be delivered via **DSL**, **cable**, or an **Ethernet connection**.

Even though the environment is smaller, it still needs to be maintained, secured, and troubleshot.
In many organizations, small networks are supported by a **local IT technician** or a **contracted professional**.

---

## 17.1.2 Device Selection for a Small Network

Like large networks, small networks must be planned and designed to meet user requirements.  
Planning should consider requirements, cost, and deployment options.

When selecting intermediary devices (like routers and switches), the module highlights these factors:

### Cost
Device cost depends on capacity and features, including:
- the number and type of ports,
- backplane performance,
- management capabilities,
- built-in security features,
- and optional advanced switching technologies.

Also consider the cost of cabling/runs needed to connect devices, and how much **redundancy** you plan to build in.

### Speed and types of ports/interfaces
Choosing the number and type of ports is critical.  
Many modern computers have **1 Gbps** NICs, and some servers may use **10 Gbps** ports.

Higher speeds cost more, but selecting Layer 2 devices that can handle higher speeds can help the network evolve without replacing core devices.

### Expandability
Network devices can be:
- **fixed configuration** (a defined set of ports/interfaces that cannot be expanded),
- or **modular** (supports expansion modules as needs grow).

Switches may provide additional ports for high-speed uplinks.
Routers may require different modules/interfaces depending on media and connectivity needs.

### Operating system features and services
Network device operating systems should support the organization’s needs, including:
- Layer 3 switching
- Network Address Translation (NAT)
- Dynamic Host Configuration Protocol (DHCP)
- Security
- Quality of service (QoS)
- Voice over IP (VoIP)

---

# 17.1.3 IP Addressing for a Small Network

When you implement a network, you should **create an IP addressing scheme** and **use it consistently**.  
Every host and device within an internetwork must have a **unique address**.

Devices that must be considered in the IP addressing scheme include:

- **End user devices** — the number and connection type (wired, wireless, remote access)
- **Servers and peripherals** — for example, printers and security cameras
- **Intermediary devices** — including switches and access points

It is recommended that you **plan, document, and maintain** an IP addressing scheme **based on device type**.  
A planned scheme makes it easier to **identify device types** and to **troubleshoot problems** (for example, when analyzing traffic with a protocol analyzer).

## Example: Consistent scheme across multiple user LANs

In the example topology, the organization requires **three user LANs**:

- `192.168.1.0/24`
- `192.168.2.0/24`
- `192.168.3.0/24`

The organization chooses to implement a consistent plan for each `192.168.x.0/24` LAN:

| Device Type | Assignable IP Address Range | Summarized as … |
|---|---|---|
| Default gateway (Router) | `192.168.x.1 – 192.168.x.2` | `192.168.x.0/30` |
| Switches (max 2) | `192.168.x.5 – 192.168.x.6` | `192.168.x.4/30` |
| Access points (max 6) | `192.168.x.9 – 192.168.x.14` | `192.168.x.8/29` |
| Servers (max 6) | `192.168.x.17 – 192.168.x.22` | `192.168.x.16/29` |
| Printers (max 6) | `192.168.x.25 – 192.168.x.30` | `192.168.x.24/29` |
| IP Phones (max 6) | `192.168.x.33 – 192.168.x.38` | `192.168.x.32/29` |
| Wired devices (max 62) | `192.168.x.65 – 192.168.x.126` | `192.168.x.64/26` |
| Wireless devices (max 62) | `192.168.x.193 – 192.168.x.254` | `192.168.x.192/26` |

The figure then shows example assignments inside `192.168.2.0/24` (such as **gateway = `192.168.2.1/24`**, **switch = `192.168.2.5/24`**, **server = `192.168.2.17/24`**, etc.).

### Why the ranges are on subnet boundaries

The assignable ranges are **deliberately aligned to subnet boundaries** to make it easier to **summarize by device group**.

Example: if another switch is added with IP `192.168.2.6`, a policy could identify *all switches* using the summarized network address:

- `192.168.x.4/30`


# 17.1.4 Redundancy in a Small Network

A key part of network design is **reliability**. Even small businesses often depend heavily on their networks for daily operations, and a network failure can be very costly.

To maintain a high degree of reliability, **redundancy** is required in the network design.  
Redundancy helps eliminate **single points of failure**.

Redundancy can be implemented in different ways, including:

- Installing **duplicate equipment**
- Supplying **duplicate network links** for critical areas

The figure highlights these examples of redundancy:

- **Redundant servers** are available in case of server failure.
- **Redundant links** provide alternate paths if a link fails.
- **Redundant switches** are present in case of switch failure.
- **Redundant routers** are available in case of router or route failure.

Small networks often have a **single exit point** to the internet through one or more default gateways.  
If the router fails, the entire network loses internet connectivity, so it may be advisable for a small business to pay for a **second service provider** as a backup.


# 17.1.5 Traffic Management

A goal of good network design (even for a small network) is to **increase employee productivity** and **minimize downtime**.  
The network administrator should consider different types of traffic and how that traffic should be treated by the network design.

Routers and switches in a small network should be configured to support **real-time traffic** (such as **voice and video**) in an appropriate way relative to other traffic. A good design will implement **Quality of Service (QoS)** to classify traffic by priority, especially during congestion.

The figure shows a priority example:

- Traffic may arrive at the router **without any priority**.
- The router classifies traffic into queues and forwards it **in order of priority** (toward the backbone network), for example:
  - **Voice** → High priority  
  - **SMTP** → Medium priority  
  - **Instant messaging** → Normal priority  
  - **FTP** → Low priority  

> Priority queuing uses four queues, and the **high-priority queue is always emptied first**.

---

# 17.1.6 Check Your Understanding — Devices in a Small Network (Module 17)

## Question 1

**Which statement correctly relates to a small network?**

- A) Small networks are complex.  
- B) The majority of businesses are small.  
- C) Small networks require an IT department to maintain.

✅ **Correct answer:** **B) The majority of businesses are small.**

**Explanation (paraphrased):**  
Small business networks are usually simpler than large enterprise networks, and many are managed by a local IT technician or a contracted professional instead of a full in-house IT department.

---
# CCNA: Introduction to Networks (ITN) — Module 17 Part 4  
## 17.1.6 Check Your Understanding (Q2–Q5) + 17.2.1–17.2.2

These notes are **paraphrased from your screenshots** (Module 17) and keep the same “study-guide” style as your previous parts.

---

## Table of Contents

- [17.1.6 Check Your Understanding — Devices in a Small Network](#1716-check-your-understanding--devices-in-a-small-network)  
  - [Question 2](#question-2)  
  - [Question 3](#question-3)  
  - [Question 4](#question-4)  
  - [Question 5](#question-5)  
- [17.2.1 Common Applications](#1721-common-applications)  
- [17.2.2 Common Protocols](#1722-common-protocols)  

---

## 17.1.6 Check Your Understanding — Devices in a Small Network

### Question 2
**Which factor must be considered when selecting network devices?**

**Options (from screen):**
- Color  
- Elasticity  
- Console connections  
- Cost  

✅ **Correct answer:** **Cost**  

**Why:** When choosing routers/switches/APs, you always have to balance features/capacity against budget (hardware cost + cabling + operations).

---

### Question 3
**What is necessary to plan and use when implementing a network?**

**Options (from screen):**
- MAC addressing scheme  
- IP addressing scheme  
- Device names  
- Printer location  

✅ **Correct answer:** **IP addressing scheme**  

**Why:** Every host/device needs a unique IP address in the internetwork. A planned scheme makes troubleshooting and growth easier.

---

### Question 4
**What is required to maintain a high degree of reliability and eliminate single points of failure?**

**Options (from screen):**
- Redundancy  
- Expandability  
- Accessibility  
- Integrity  

✅ **Correct answer:** **Redundancy**  

**Why:** Redundancy adds alternate paths/devices so that one failure doesn’t take the whole network down.

---

### Question 5
**What is required to classify traffic according to priority?**

**Options (from screen):**
- Routing  
- Quality of service (QoS)  
- IP addressing scheme  
- Switching  

✅ **Correct answer:** **Quality of service (QoS)**  

**Note (from your attempt):** You selected **Routing**, which is marked incorrect on the screen.

**Why:** **QoS** is the set of mechanisms used to **classify and prioritize** certain traffic types (for example, voice/video vs. file transfers) so important flows get served first during congestion.

---

## 17.2.1 Common Applications

After a small network is installed, it still needs **applications** and **services** to be useful.

### Two “application” categories you’ll see on networks
- **Network applications**  
  Apps that communicate across the network (and may directly use application-layer protocols).  
  Examples: **web browsers**, **email clients**, collaboration tools.

- **Application layer services**  
  Background services that interface with the network and help apps use network resources (often “invisible” to the user).  
  Examples: file/print services, name resolution services, authentication services.

### Why protocols matter
Every app or service relies on **protocols** that define:
- the **rules** of communication  
- the **data formats** used  
- how endpoints understand each other (a “common language”)

Without protocols, devices would not have a consistent way to format data, send it, and interpret it.

### Practical observation (Windows)
You can view active applications/processes/services with **Task Manager**, which helps you understand what is running and potentially generating network traffic.

**Tip:** When troubleshooting “slow network” complaints, checking running apps/services is a quick way to spot heavy usage (sync clients, browsers with many tabs, meetings, downloads, etc.).

---

## 17.2.2 Common Protocols

A technician’s daily work (in small or large networks) involves network protocols because protocols support:
- the **applications** used by employees  
- the **services** the business depends on

### Common remote access protocols
Network admins often need to remotely manage devices and servers.

- **Telnet**  
  Remote terminal access, but **not secure** (traffic is sent in plaintext).

- **SSH (Secure Shell)**  
  A secure alternative to Telnet. With SSH, admins connect to a device **as if locally logged in**, but the session is **encrypted**.

### What must support SSH?
SSH works between an **SSH client** and an **SSH server**.

- **Network device (router/switch/AP, etc.)** must support SSH to provide **SSH server** access to clients.
- **Server (web/email/etc.)** can also run SSH services so admins can securely manage it.

### Common network servers and “typical” related protocols
The screenshot shows a small network with common server roles:

| Server role | What it provides | Typical protocols | Common ports (defaults) |
|---|---|---|---|
| Web Server | Websites/web apps | HTTP / HTTPS | 80 / 443 |
| Email Server | Email transport + mailbox access | SMTP / IMAP / POP3 | 25 / 143 / 110 |
| FTP Server | File transfer | FTP | 21 (control) |
| DHCP Server | Automatic IP addressing | DHCP | 67/68 (UDP) |
| DNS Server | Name ↔ IP resolution | DNS | 53 (UDP/TCP) |

> **Exam habit:** Know the *server role → protocol → port* pattern. It shows up constantly in CCNA-style questions.

### SSH quick facts to remember
- SSH provides **encrypted remote CLI access** (confidentiality + integrity).
- SSH uses **TCP port 22** by default.
- Telnet uses **TCP port 23** and is considered insecure for management.

---
# CCNA ITN — Module 17 (Build a Small Network)
## Part 5 — 17.2.2 Common Protocols (Common Network Servers) + 17.2.3 Voice and Video Applications

> This part sticks strictly to the screenshots you sent and **paraphrases** the content (same structure + key details).

---

## 17.2.2 Common Protocols — Common Network Servers and Their Protocols

Network servers often provide the core services employees rely on in a small business network.  
Also, **one server can run multiple services** (for example: email + FTP + SSH on the same box).

### Web Server
- Web browsers (clients) and web servers exchange web traffic using **HTTP**.
- For secure web communication, use **HTTPS** (HTTP + security).

### Email Server
- Email servers and clients use **SMTP** to **send** email.
- Email clients use **POP3** or **IMAP** to **retrieve** email.
- Recipients are written in the common email format: `user@xyz.xxx`.

### FTP Server
- **FTP** is used for **uploading and downloading files** between an FTP client and an FTP server.
- Secure variants exist for safer file transfers:
  - **FTPS** (FTP Secure)
  - **SFTP** (Secure FTP)

### DHCP Server
- **DHCP** lets clients automatically obtain their IP configuration from a DHCP server, such as:
  - IP address
  - subnet mask
  - default gateway
  - and other settings

### DNS Server
- **DNS** translates (resolves) a **domain name** into an **IP address**  
  Example shown: `cisco.com` → `72.163.4.185`.
- DNS provides the IP address of a website (domain name) to the device that requested it.

---

### Why these protocols matter (what a protocol defines)
These protocols are part of the “core toolkit” for a network professional. Each protocol defines things like:
- The processes at both ends of a communication session
- The different message types
- Message syntax (format)
- The meaning of information fields
- How messages are sent and what response is expected
- How the protocol interacts with the next lower layer

### Security best practice mentioned
Many organizations create a policy to use **secure versions** of protocols whenever possible, for example:
- **SSH** instead of Telnet
- **SFTP** instead of FTP
- **HTTPS** instead of HTTP

---

## 17.2.3 Voice and Video Applications

Modern businesses increasingly use **IP telephony** and **streaming media** to communicate with customers and partners.  
Many employees also work remotely, so they still need access to:
- Corporate software and files
- Voice and video support

The network administrator must make sure:
- The right equipment is installed in the network
- Devices are configured to support **priority delivery** (real-time traffic needs priority)

### Factors to consider for real-time applications

#### Infrastructure
- The network infrastructure must be able to support real-time applications.
- Existing devices and cabling should be tested and validated.
- You may need newer networking products.

#### VoIP
- VoIP devices convert **analog** phone signals into **digital IP packets**.
- VoIP is usually cheaper than a full IP telephony solution, but the quality may not meet the same standards.
- For small networks, voice/video over IP can be handled with tools like **Skype** and non-enterprise versions of **Cisco WebEx**.

#### IP Telephony
- An IP phone performs voice-to-IP conversion and uses a **dedicated server** for call control and signaling.
- Vendors provide small-business IP telephony solutions (example shown: **Cisco Business Edition 4000 Series** products).

#### Real-Time Applications
- The network should support **QoS** mechanisms to reduce latency issues for real-time streaming.
- Two protocols that help support real-time delivery are:
  - **RTP** (Real-Time Transport Protocol)
  - **RTCP** (Real-Time Transport Control Protocol)


---

# CCNA – Build a Small Network (Module 17) — Part 6  
## 17.2.4 Check Your Understanding + 17.3 Scale to Larger Networks (17.3.1–17.3.4)

> Notes are paraphrased from your screenshots and keep the same order/structure.

---

## Table of Contents

- [17.2.4 Check Your Understanding – Small Network Applications and Protocols](#1724-check-your-understanding--small-network-applications-and-protocols)  
- [17.3 Scale to Larger Networks](#173-scale-to-larger-networks)  
  - [17.3.1 Small Network Growth](#1731-small-network-growth)  
  - [17.3.2 Protocol Analysis](#1732-protocol-analysis)  
  - [17.3.3 Employee Network Utilization](#1733-employee-network-utilization)  
  - [17.3.4 Check Your Understanding – Scale to Larger Networks](#1734-check-your-understanding--scale-to-larger-networks)  

---

## 17.2.4 Check Your Understanding – Small Network Applications and Protocols

### Question 1  
**What are two forms of software programs or processes that provide access to the network? (Choose two.)**

Options:
- Gaming software  
- Productivity software  
- Application layer services  
- Virtual machine software  
- Network applications  
- Antivirus software  

✅ **Correct answers:**
- **Network applications**
- **Application layer services**

**Why:** A network is “useful” because of the apps and services running on it. End-user apps (like email clients/web browsers) are **network applications**, and some functions work through **application layer services** that support app communication and resource access (like file transfer or printing support).

---

### Question 2  
**Which two network protocols are used to establish a remote access network connection to a device? (Choose two.)**

Options:
- Simple Mail Transfer Protocol (SMTP)  
- File Transfer Protocol (FTP)  
- Hypertext Transfer Protocol (HTTP)  
- Remote Connect (RC)  
- Telnet  
- Secure Shell (SSH)  

✅ **Correct answers:**
- **Telnet**
- **Secure Shell (SSH)**

**Why:** These are the classic remote-access protocols used by administrators to connect to and manage network devices. **SSH** is the secure alternative to **Telnet**.

---

## 17.3 Scale to Larger Networks

### 17.3.1 Small Network Growth

If a small business grows, its network usually needs to **grow with it** (scaling). To scale smoothly, the admin needs enough planning time to make good decisions aligned with business growth.

To scale a network, key elements should be in place:

- **Network documentation**  
  Keep **physical and logical topology** information so everyone knows how the network is built and how it *should* behave.

- **Device inventory**  
  Maintain a list of the devices that **use or make up** the network (routers, switches, APs, servers, endpoints, etc.).

- **Budget**  
  Have an **itemized IT budget**, including planned equipment purchases for the fiscal year.

- **Traffic analysis**  
  Document the **protocols, applications, and services** being used, and their **traffic requirements**.

These elements support the decision-making needed to expand without breaking performance or reliability.

---

### 17.3.2 Protocol Analysis

As the network grows, it becomes important to understand:

- what traffic types are on the network
- how traffic is flowing right now

Many network management tools exist, but even a **protocol analyzer** (like **Wireshark**) can help.

Example idea from the screenshot:
- Running Wireshark on key hosts can reveal protocol usage.
- A protocol hierarchy view can show the host using **IPv6 and IPv4**, and (for IPv4 traffic) activity such as **DNS, SSL, HTTP, ICMP**, and more.

To identify traffic flow patterns, do things like:
- **Capture traffic during peak utilization times** so you see realistic “busy hour” behavior.
- **Capture on different segments and devices**, because some traffic is local to a particular segment/area.

How you use the results:
- Evaluate traffic based on **source/destination** and **traffic type**.
- Make decisions to manage traffic more efficiently, such as:
  - reducing unnecessary flows, or
  - changing flow patterns (for example, moving a server to a different segment)

Sometimes simply **relocating a service/server** improves performance and supports growth. Other times, growth requires a larger redesign and more significant changes.

---

### 17.3.3 Employee Network Utilization

Beyond traffic trends, an admin should also track **how employees actually use the network** and how that usage changes over time.

Many operating systems have built-in tools to display this information. For example, Windows hosts can use:
- **Task Manager**
- **Event Viewer**
- **Data Usage** tools

These tools help capture “snapshot” information like:
- OS and OS version
- CPU utilization
- RAM utilization
- Drive utilization
- Non-network applications
- Network applications

Why it matters:
- Documenting snapshots over time helps identify changing protocol requirements and traffic flows.
- If resource usage shifts (CPU/RAM/network), the admin may need to adjust network resource allocation.

Windows 10 detail from the screenshot:
- The **Data Usage** tool helps determine which applications are using network services on a host.
- Access path: **Settings > Network & Internet > Data usage > (choose the network interface)**  
  This view typically shows usage for the **last 30 days**.

---

### 17.3.4 Check Your Understanding – Scale to Larger Networks

#### Question 1  
**Which elements are required to scale to a larger network? (Choose two.)**

Options:
- Increased bandwidth  
- Budget  
- Device configurations  
- Network documentation  
- Windows hosts  

✅ **Correct answers:**
- **Budget**
- **Network documentation**

---

#### Question 2  
**Which software installed on key hosts can reveal the types of network traffic flowing through the network?**

Options:
- Windows  
- Wireshark  
- SSH  
- Linux  
- MacOS  

✅ **Correct answer:** **Wireshark**

---

#### Question 3  
**What Windows 10 tool is useful to determine which applications are using network services on a host?**

Options:
- Windows Defender Firewall  
- Data Usage  
- Control panel  
- File Manager  
- Windows Explorer  

✅ **Correct answer:** **Data Usage**


# CCNA: Introduction to Networks (ITN) — Module 17: Build a Small Network (Part 7)

> **Scope (Part 7):** 17.4.1 – 17.4.4 (Verify Connectivity)

## Table of Contents
- [17.4 Verify Connectivity](#174-verify-connectivity)
  - [17.4.1 Verify Connectivity with Ping](#1741-verify-connectivity-with-ping)
  - [17.4.2 Extended Ping](#1742-extended-ping)
  - [17.4.3 Verify Connectivity with Traceroute](#1743-verify-connectivity-with-traceroute)
  - [17.4.4 Extended Traceroute](#1744-extended-traceroute)

---

## 17.4 Verify Connectivity

Whether your network is small and new, or you are scaling an existing network, you need a way to verify that devices are connected to each other (and to the internet). This topic covers common utilities used to test connectivity and troubleshoot where a problem exists.

---

## 17.4.1 Verify Connectivity with Ping

### What ping does
- Ping is an effective way to quickly test **Layer 3 connectivity** between a source and destination IP address.
- Ping also provides **round-trip time (RTT)** statistics.

### What ping uses
- Ping uses **Internet Control Message Protocol (ICMP)**:
  - **Echo Request** (ICMP Type 8)
  - **Echo Reply** (ICMP Type 0)

### OS behavior (Windows example)
- Ping exists on many operating systems (Windows, Linux, macOS) and Cisco IOS.
- On a Windows 10 host, ping sends **four** consecutive ICMP echo requests and expects **four** consecutive echo replies.

### Example (Windows output — abridged)
```text
C:\Users\PC-A> ping 10.1.1.10
Reply from 10.1.1.10: bytes=32 time=47ms TTL=51
Reply from 10.1.1.10: bytes=32 time=60ms TTL=51
...
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
Minimum = 47ms, Maximum = 60ms, Average = 52ms
```

### Cisco IOS ping behavior + indicators
- Cisco IOS ping output differs from Windows. In the example shown, IOS sends **five** ICMP echo messages.
- IOS prints an indicator character for each attempt. Common indicators shown:

| IOS Indicator | Meaning |
|---|---|
| `!` | Echo reply received successfully (validates Layer 3 connectivity) |
| `.` | Timeout waiting for an echo reply (suggests a connectivity problem along the path) |
| `U` | A router responded with ICMP Type 3 “destination unreachable” |

**About `U` (destination unreachable)**
- Possible reasons listed include:
  - The router does not know the direction (route) to the destination network
  - The router could not find the host on the destination network

> **Note:** Other possible ping reply characters can include `Q`, `M`, `?`, or `&`, but their meanings are out of scope for this module.

---

## 17.4.2 Extended Ping

### Standard ping source behavior
- A standard ping uses the IP address of the interface **closest to the destination network** as the source IP.

**Example shown**
- When R1 pings **10.1.1.10**, the standard ping source address on R1 is the **G0/0/0** interface (example IP shown: **209.165.200.225**).

### What “extended ping” is (Cisco IOS)
- Cisco IOS supports an “extended” mode of ping that lets you customize ping operation parameters (including selecting a different source address).

### How to run an extended ping
1. Enter privileged EXEC mode.
2. Type `ping` **without** specifying a destination IP.
3. Answer the prompts (press **Enter** to accept defaults).

### Why you’d use it
- If you want to test connectivity from a specific network/interface (for example, from the **R1 LAN 192.168.10.0/24**), you can set the extended ping’s source IP to the LAN interface IP (example shown: **192.168.10.1**).

### Example (prompt-driven output — abridged)
```text
R1# ping
Protocol [ip]:
Target IP address: 10.1.1.10
Repeat count [5]:
Datagram size [100]:
Timeout in seconds [2]:
Extended commands [n]: y
Ingress ping [n]:
Source address or interface: 192.168.10.1
...
```

**IPv6 note**
- The module notes that `ping ipv6` is used for **IPv6 extended pings**.

---

## 17.4.3 Verify Connectivity with Traceroute

### Why traceroute is needed
- Ping can quickly tell you if there is a Layer 3 connectivity problem, but it does **not** identify *where* the problem is.
- Traceroute helps locate Layer 3 problem areas by returning a list of **hops** as traffic is routed through the network.

### Syntax differences
- Windows: `tracert <destination>`
- Cisco IOS: `traceroute <destination>`

### Example (Windows tracert — abridged)
```text
C:\Users\PC-A> tracert 10.1.1.10
1   ...   192.168.10.1
2   *  *  *  Request timed out.
3   *  *  *  Request timed out.
```

**Interpretation notes (as shown)**
- The gateway responded, but the next hop timed out (asterisks).
- Timeouts can mean a failure beyond the LAN, or that routers are configured not to respond to the trace probes used.

### Interrupting traceroute
- Windows: **Ctrl+C**
- Cisco IOS: **Ctrl+Shift+6**

### Implementation note (Windows vs IOS/Linux)
- Windows `tracert` sends **ICMP Echo Requests**.
- Cisco IOS and Linux use **UDP** (to an invalid port), and the final destination returns an **ICMP port unreachable** message.

---

## 17.4.4 Extended Traceroute

### What extended traceroute adds
Extended traceroute lets you adjust traceroute parameters and is helpful for:
- troubleshooting routing loops,
- determining the exact next-hop router,
- finding where packets are dropped or denied by a router/firewall.

### Windows: tracert options (from `tracert /?`)
Windows supports several options via command-line switches, including:
- `-d` — Do not resolve addresses to hostnames
- `-h maximum_hops` — Maximum number of hops to search for target
- `-j host-list` — Loose source route (IPv4-only)
- `-w timeout` — Wait timeout (milliseconds) for each reply
- `-R` — Trace round-trip path (IPv6-only)
- `-S srcaddr` — Source address to use (IPv6-only)
- `-4` — Force IPv4
- `-6` — Force IPv6

### Cisco IOS: prompt-driven extended traceroute
- On Cisco IOS, type `traceroute` **without** a destination IP address.
- IOS guides you through prompts to set traceroute parameters (press Enter to accept defaults).
- A common use-case shown is setting a specific **source address** (example: **192.168.10.1**) when tracing to a destination (example: **10.1.1.10**).

---
# CCNA: Introduction to Networks (ITN) — Module 17: Build a Small Network (Part 8)

> **Scope (Part 8):** 17.4.5 – 17.5.1 (Network Baseline, Lab, and Windows Host IP Commands)

## Table of Contents
- [17.4.5 Network Baseline](#1745-network-baseline)
- [17.4.6 Lab — Test Network Latency with Ping and Traceroute](#1746-lab--test-network-latency-with-ping-and-traceroute)
- [17.5 Host and IOS Commands](#175-host-and-ios-commands)
  - [17.5.1 IP Configuration on a Windows Host](#1751-ip-configuration-on-a-windows-host)

---

## 17.4.5 Network Baseline

### What a baseline is
- A network baseline is one of the most effective tools for **monitoring** and **troubleshooting** network performance.
- You build it over time by measuring performance at different times and load levels to understand “normal” behavior.

### How command outputs support a baseline
- Outputs from network commands contribute data to the baseline.
- A simple way to begin is to copy/paste results from commands like:
  - `ping`
  - `tracert` / `traceroute`
  - other relevant utilities
- Save the results into a text file, and **timestamp** them (date + time) so you can compare later.

### What to compare
- Error messages (if any)
- Host-to-host response times
- Signs of increasing latency

### Example (baseline comparison concept)
**Baseline capture #1**
- Timestamp shown: **August 19, 2019 at 08:14:43**
- Ping RTTs shown are **less than 1 ms**.

**Baseline capture #2 (one month later)**
- Timestamp shown: **September 19, 2019 at 10:18:21**
- Ping RTTs shown are around **46–50 ms** (average around **48 ms**).

**Interpretation**
- Much longer RTTs compared to the earlier baseline can indicate a **potential problem**.

### Best-practice note
- Corporate networks typically maintain extensive baselines, and professional monitoring tools exist for this.
- Cisco suggests searching for “Baseline Process Best Practices”.

---

## 17.4.6 Lab — Test Network Latency with Ping and Traceroute

### Lab objectives
- **Part 1:** Use **Ping** to document network latency  
- **Part 2:** Use **Traceroute** to document network latency  

### What you need
- 1 PC with Internet access (and permission to test, where required).

### Part 1 — Use Ping to Document Network Latency

**Step 1: Verify connectivity**
- Example shown: `ping www.cisco.com`

**Step 2: Collect latency data to RIR websites**
The lab uses these destinations:
- `www.lacnic.net` (LACNIC)
- `www.afrinic.net` (AFRINIC)
- `www.apnic.net` (APNIC)

> Note: The lab mentions some RIR sites may not respond to ICMP echo requests, so you may need to use the responsive ones.

**Step 3: Send 25 echo requests and save output**
Example command pattern (Windows):
```bat
ping -n 25 www.lacnic.net > ping_lacnic.txt
ping -n 25 www.afrinic.net > ping_afrinic.txt
ping -n 25 www.apnic.net  > ping_apnic.txt
```

**IPv4 forcing example**
- The lab also shows using `-4` to force IPv4 name resolution:
```bat
ping -n 25 -4 www.lacnic.net > ping_lacnic.txt
```

**Step 4: Confirm and review the files**
- Confirm creation:
```bat
dir *.txt
```
- View a file:
```bat
more ping_lacnic.txt
```

**Step 5: Record your findings**
For each destination, record:
- Minimum RTT
- Maximum RTT
- Average RTT

You can capture your results like this:

| Destination | Min RTT (ms) | Max RTT (ms) | Avg RTT (ms) |
|---|---:|---:|---:|
| LACNIC |  |  |  |
| AFRINIC |  |  |  |
| APNIC |  |  |  |

---

### Part 2 — Use Traceroute to Document Network Latency

**Step 1: Run tracert and save output**
Example pattern:
```bat
tracert www.lacnic.net > trace_lacnic.txt
tracert www.afrinic.net > trace_afrinic.txt
tracert www.apnic.net  > trace_apnic.txt
```

**Step 2: Review hop-by-hop behavior**
- View files:
```bat
more trace_lacnic.txt
```
- Compare where delays appear (which hops show higher RTT or timeouts).

---

### Traceroute option test (shown)
**Disable reverse DNS lookups**
- The lab demonstrates:
```bat
tracert -d www.lacnic.net
```
- This shows IP addresses without attempting hostname resolution, which can make results faster/cleaner.

---

## 17.5 Host and IOS Commands

This section introduces common host tools (Windows shown here) that help you validate IP configuration and troubleshoot connectivity issues.

---

## 17.5.1 IP Configuration on a Windows Host

### GUI method (quick check)
In Windows 10, you can view addressing details in the adapter/connection details to quickly see key settings such as:
- IP address
- Subnet mask
- Default gateway (router)
- DNS server

### `ipconfig` (basic)
Admins commonly use `ipconfig` from the command line to view key IP settings.

**Example shown (abridged)**
- IPv4 address: **192.168.10.10**
- Subnet mask: **255.255.255.0**
- Default gateway: **192.168.10.1**
- Link-local IPv6 address is also displayed.

### `ipconfig /all` (detailed)
`ipconfig /all` provides more details, such as:
- Host name and DNS suffix info (example DNS suffix shown: **cisco.com**)
- Adapter description and status
- Physical (MAC) address (example shown: **F8-94-C2-E4-C5-0A**)
- DHCP enabled status and lease details
- Default gateway, DHCP server, and DNS servers (example DNS server shown: **192.168.10.1**)
- NetBIOS over TCP/IP status

### DHCP renew workflow
If the host is a DHCP client, the IP configuration can be refreshed using:
```bat
ipconfig /release
ipconfig /renew
```

### DNS cache display
Windows DNS Client can cache previously resolved names. You can view the cache with:
```bat
ipconfig /displaydns
```

**Example cache entry shown (abridged)**
- Record name: `netacad.com`
- Record type: 1 (A record)
- TTL shown
- A (Host) record resolves to: **54.165.95.219**

---

# CCNA: Introduction to Networks (ITN) — Module 17: Build a Small Network  
## Part 9 — 17.5.2 to 17.5.5 (Host and IOS Commands)

> Notes are paraphrased from your provided NetAcad screenshots.

---

## 17.5.2 IP Configuration on a Linux Host

Verifying IP settings in a Linux GUI depends on the **distribution (distro)** and the **desktop environment**.

In a typical “Connection Information” window (example: Ubuntu GNOME), you can see:
- **Interface name** (example: `enp0s3`)
- **MAC address** (hardware address)
- **Driver / link speed / security**
- **IPv4 details**: IP address, broadcast address, subnet mask, default route (gateway), DNS
- **IPv6 details** (often at least a link-local address)

### Common CLI checks (Linux)

Network admins often use `ifconfig` to check active interfaces and their IP configuration.

```bash
ifconfig
```

Modern Linux systems also commonly use the `ip` utility. The `ip address` command displays interface addresses and their properties, and it can also be used to add/remove addresses.

```bash
ip address
# (short form)
ip a
```

> Note: Output varies by distro and system configuration.

---

## 17.5.3 IP Configuration on a macOS Host

### GUI check (macOS)

A common path is:
- **Network Preferences** → select interface (e.g., Wi‑Fi) → **Advanced…**
- Review the TCP/IP settings (example shown using DHCP): IPv4 address, subnet mask, router (default gateway), and options like renewing a DHCP lease.

### Common CLI checks (macOS)

Check the IP configuration of an interface (example interface: `en0`):

```bash
ifconfig en0
```

List network services:

```bash
networksetup -listallnetworkservices
```

> Asterisks (`*`) in the list indicate a network service is disabled.

Get detailed configuration for a specific service (example: Wi‑Fi):

```bash
networksetup -getinfo Wi-Fi
```

---

## 17.5.4 The `arp` Command

The `arp` command shows what the host currently knows in its **ARP cache** (IPv4 → MAC mappings), including whether entries are **dynamic** or **static**.

- Can be run from Windows, Linux, or macOS command line/terminal.
- The cache often includes:
  - IPv4 address
  - Physical address (MAC)
  - Type (dynamic/static)

### Example command

```bash
arp -a
```

### Important behavior to remember
- **ARP caches are not full network inventories.**  
  They usually only contain devices the host has **recently communicated with**.
- If a device is missing from the ARP output, generate traffic to it (for example, **ping it**) so the host learns (or refreshes) the ARP entry.

### Clearing ARP cache (Windows example)

Windows can clear the ARP cache using a `netsh` command:

```powershell
netsh interface ip delete arpcache
```

> Note: You may need administrator privileges.

---

## 17.5.5 Common `show` Commands Revisited (Cisco IOS)

Cisco IOS provides many `show` commands to verify device operation (routers/switches), including configuration, interface health, routing, and general status. These commands are heavily used in troubleshooting.

### Common commands and what they’re used for

| Command | Useful for… |
|---|---|
| `show running-config` | Verify the current configuration and settings |
| `show interfaces` | Verify interface status and check for errors |
| `show ip interface` | Verify Layer 3 information for an interface |
| `show arp` | Verify the list of known hosts on local Ethernet LANs |
| `show ip route` | Verify Layer 3 routing information |
| `show protocols` | Verify which protocols are operational |
| `show version` | Verify memory, interfaces, and licenses (plus basic platform/IOS details) |

> Note: Example outputs in course materials are often edited to focus on the relevant fields.


---

# CCNA: Introduction to Networks (ITN) — Module 17: Build a Small Network  
## Part 10 — 17.5.5 to 17.5.7 (IOS show Commands + CDP)

> Notes are paraphrased from your provided NetAcad screenshots.

> **Scope note:** The command outputs below are *examples* (your device output can differ by platform, IOS version, and configuration).

---

## 17.5.5 Common `show` Commands Revisited (Cisco IOS)

### `show running-config`
**Use it to:** verify the *current* (active) configuration and settings.

**What you typically confirm:** hostname, interface IPs/descriptions, routing, banners, line settings (console/VTY), and security basics.

**Example output (excerpt):**
```text
R1# show running-config
(Output omitted)

version 15.5
service timestamps debug datetime msec
service timestamps log datetime msec
service password-encryption

hostname R1

interface GigabitEthernet0/0/0
 description Link to R2
 ip address 209.165.200.225 255.255.255.252
 negotiation auto

interface GigabitEthernet0/0/1
 description Link to LAN
 ip address 192.168.10.1 255.255.255.0
 negotiation auto

router ospf 10
 network 192.168.10.0 0.0.0.255 area 0
 network 209.165.200.224 0.0.0.3 area 0

banner motd ^C Authorized access only! ^C

line con 0
 password 7 14141B180F0B
 login
line vty 0 4
 password 7 00071A150754
 login
 transport input telnet ssh

end
R1#
```

---

### `show interfaces`
**Use it to:** verify interface status and find errors (physical/data link issues).

**What you typically check:**
- `is up, line protocol is up` (interface and protocol are operational)
- speed/duplex, MTU
- input/output errors, CRCs, drops, collisions, resets

**Example output (excerpt):**
```text
R1# show interfaces
GigabitEthernet0/0/0 is up, line protocol is up
  Hardware is ISR4321-2x1GE, address is a0e0.af0d.e140 (bia a0e0.af0d.e140)
  Description: Link to R2
  Internet address is 209.165.200.225/30
  MTU 1500 bytes, BW 100000 Kbit/sec, DLY 100 usec,
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation ARPA
  Full Duplex, 100Mbps, media type is RJ45
  ...
  0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
  ...
GigabitEthernet0/0/1 is up, line protocol is up
(Output omitted)
```

---

### `show ip interface`
**Use it to:** verify Layer 3 details and IP-related behavior on an interface.

**What you typically check:** IP/prefix, helper address, directed broadcast, ACLs applied, Proxy ARP, ICMP behavior, CEF/fast switching, and other IP features.

**Example output (excerpt):**
```text
R1# show ip interface
GigabitEthernet0/0/0 is up, line protocol is up
  Internet address is 209.165.200.225/30
  Broadcast address is 255.255.255.255
  MTU is 1500 bytes
  Helper address is not set
  Directed broadcast forwarding is disabled
  Multicast reserved groups joined: 224.0.0.5 224.0.0.6
  Inbound access list is not set
  Outgoing access list is not set
  Proxy ARP is enabled
  ...
GigabitEthernet0/0/1 is up, line protocol is up
(Output omitted)
```

---

### `show arp`
**Use it to:** verify the list of known hosts on local Ethernet LANs (IPv4-to-MAC bindings).

**What you typically check:**
- Does the router have an ARP entry for the host you’re trying to reach?
- Does the entry map to the expected interface?
- Is the MAC address reasonable for that segment?

**Example output:**
```text
R1# show arp
Protocol  Address          Age (min)  Hardware Addr   Type  Interface
Internet  192.168.10.1      -         a0e0.af0d.e141  ARPA  GigabitEthernet0/0/1
Internet  192.168.10.10     95        c07b.bcc4.a9c0  ARPA  GigabitEthernet0/0/1
Internet  209.165.200.225   -         a0e0.af0d.e140  ARPA  GigabitEthernet0/0/0
Internet  209.165.200.226   138       a03d.6fe1.9d90  ARPA  GigabitEthernet0/0/0
R1#
```

---

### `show ip route`
**Use it to:** verify Layer 3 routing information (connected routes, learned routes, default route, next hops).

**What you typically check:**
- Is the destination network present?
- Which protocol learned it (C/L/O/S/etc.)?
- What is the next hop and outgoing interface?
- Is there a default route (`0.0.0.0/0`) if needed?

**Example output (excerpt):**
```text
R1# show ip route
Gateway of last resort is 209.165.200.226 to network 0.0.0.0

O*E2 0.0.0.0/0 [110/1] via 209.165.200.226, GigabitEthernet0/0/0
O    10.1.1.0/24 [110/3] via 209.165.200.226, GigabitEthernet0/0/0
C    192.168.10.0/24 is directly connected, GigabitEthernet0/0/1
L    192.168.10.1/32 is directly connected, GigabitEthernet0/0/1
C    209.165.200.224/30 is directly connected, GigabitEthernet0/0/0
L    209.165.200.225/32 is directly connected, GigabitEthernet0/0/0
O    209.165.200.228/30 [110/2] via 209.165.200.226, GigabitEthernet0/0/0
R1#
```

---

### `show protocols`
**Use it to:** quickly confirm which protocols are operational and the addresses/statuses of interfaces.

**Example output:**
```text
R1# show protocols
Global values:
  Internet Protocol routing is enabled
GigabitEthernet0/0/0 is up, line protocol is up
  Internet address is 209.165.200.225/30
GigabitEthernet0/0/1 is up, line protocol is up
  Internet address is 192.168.10.1/24
Serial0/1/0 is down, line protocol is down
Serial0/1/1 is down, line protocol is down
GigabitEthernet0 is administratively down, line protocol is down
R1#
```

---

### `show version`
**Use it to:** verify device platform details: IOS version, uptime, system image, memory, interfaces, and licensing info.

**Example output (excerpt):**
```text
R1# show version
Cisco IOS XE Software, Version 03.16.08.S - Extended Support Release
Cisco IOS Software, ISR Software (X86_64_LINUX_IOSD-UNIVERSALK9-M), Version 15.5(3)S8
...
ROM: IOS-XE ROMMON
R1 uptime is 2 hours, 25 minutes
System image file is "bootflash:/isr4300-universalk9.03.16.08.S.155-3.S8-ext.SPA.bin"
...
2 Gigabit Ethernet interfaces
2 Serial interfaces
...
Configuration register is 0x2102
R1#
```

---

## 17.5.6 The `show cdp neighbors` Command

**CDP (Cisco Discovery Protocol)** helps you learn about *directly connected Cisco devices* on a link.

### What CDP can show about a neighbor
- **Device ID** (neighbor hostname)
- **Local interface** and neighbor **port ID**
- **Capabilities** (router/switch, etc.)
- **Platform** (hardware model)

### Example: `show cdp neighbors`
```text
R3# show cdp neighbors
Capability Codes: R - Router, T - Trans Bridge, B - Source Route Bridge
                 S - Switch, H - Host, I - IGMP, r - Repeater, P - Phone,
                 D - Remote, C - CVTA, M - Two-port Mac Relay

Device ID  Local Intrfce  Holdtme  Capability  Platform    Port ID
S3         Gig 0/0/1      122      S I         WS-C2960+   Fas 0/5

Total cdp entries displayed : 1
R3#
```

### `show cdp neighbors detail`
- Shows **more information**, including the neighbor **IP address**.
- Useful when you can’t yet route across a link, but you still need to identify what’s connected.

### Security note + disabling CDP
CDP can expose helpful infrastructure details to attackers if it’s enabled everywhere.

- **Disable CDP globally:**
  ```text
  no cdp run
  ```
- **Disable CDP on an interface:**
  ```text
  interface <name>
   no cdp enable
  ```

---

## 17.5.7 The `show ip interface brief` Command

One of the most-used commands for a fast interface health check. It provides a compact summary of:
- Interface name
- IP address (if any)
- Method (manual/DHCP/unset)
- Status / Protocol (Layer 1 + Layer 2/3 state)

### Router example
```text
R1# show ip interface brief
Interface              IP-Address       OK? Method Status                Protocol
GigabitEthernet0/0/0   209.165.200.225  YES manual up                    up
GigabitEthernet0/0/1   192.168.10.1     YES manual up                    up
Serial0/1/0            unassigned       NO  unset  down                  down
Serial0/1/1            unassigned       NO  unset  down                  down
GigabitEthernet0       unassigned       YES unset  administratively down  down
R1#
```

### Switch example
```text
S1# show ip interface brief
Interface       IP-Address         OK? Method Status  Protocol
Vlan1           192.168.254.250    YES manual up      up
FastEthernet0/1 unassigned         YES unset  down    down
FastEthernet0/2 unassigned         YES unset  up      up
FastEthernet0/3 unassigned         YES unset  up      up
S1#
```

### How to interpret the quick status
- **`up/up`** = the interface is operational.
- **`administratively down`** = the interface is shut down (`shutdown` applied).
- **`down/down`** (switch ports) often means no cable/device, or the far end is down.


---

# CCNA 1 (ITN) — Module 17: Build a Small Network  
## Part 11 — Host and IOS Commands + Troubleshooting (17.5.8–17.6.4)

### Sections in this file
- **17.5.8** Video — The **show version** Command  
- **17.6** Troubleshooting Methodologies  
  - **17.6.1** Basic Troubleshooting Approaches  
  - **17.6.2** Resolve or Escalate?  
  - **17.6.3** The **debug** Command  
  - **17.6.4** The **terminal monitor** Command  

---

## 17.5.8 Video — The **show version** Command

The **show version** command helps verify and troubleshoot basic hardware and software details during the boot process.

### Video transcript (English)

00:04 — In this demonstration, a terminal emulator (**Tera Term**) is used to access the **console CLI** of a **Cisco 4321** router.  
00:14 — Press **Enter**, type **enable**, then run **show version** from **privileged EXEC** mode to display router information.  
00:25 — Just below the `show version` command, you can see the **Cisco IOS software version** running on the router.  
00:33 — The output shows the router is running a **UNIVERSALK9** image, which includes the base IOS features **plus strong cryptography support**.  
00:45 — This output is from an **extended maintenance / extended support** release (example shown: **major 16, minor 6, rebuild 4**).  
00:55 — The router’s **uptime** is shown (example: the router has been up for about **33 minutes**).  
01:01 — Press the **space bar** to display more output.  
01:04 — More output shows the **IOS image filename** and where it is stored.  
01:12 — `isr4300` refers to the **hardware platform** the image was built for (the example device is a **4321** router).  
01:21 — The filename details are reviewed again.  
01:26 — **SPA** in the filename indicates the image was **digitally signed**.  
01:33 — The **.bin** at the end of the filename indicates a **binary** file format.  
01:38 — The output shows the **last reload reason** (example: the `reload` command was used). This can be helpful in hardware troubleshooting, especially if a router is crashing or freezing.  
01:51 — The output includes information about the router’s **cryptographic capabilities**.  
01:55 — Press the **space bar** again to see the remaining output.  
02:00 — Next, the **license information** is displayed. It is divided into:
- **Suite licenses**
- **Technology package licenses**

02:10 — The technology package license section is examined first.  
02:13 — The example shows a **permanent** license for `ipbasek9`, which is the default feature set / feature package specified when the router was ordered.  
02:26 — The output shows the license will remain available after the **next reboot**.  
02:32 — The example indicates there are **no other permanent or evaluation** licenses installed.  
02:36 — If you wanted to upgrade IOS or add features, an example **three-step process** is:
1) Purchase the software package and obtain a **Product Activation Key (PAK)**  
2) Obtain a license using your **PAK** and the device **UDI** (Unique Device Identifier)  
3) Install the license  

03:00 — A **suite license** could be purchased to enable multiple functions; if installed, that information would appear in the suite license area.  
03:08 — The output shows about **2 GB of DRAM**, split between:
- **Main memory** (used by the CPU to run IOS, and stores items like the running configuration and routing table)
- **Shared memory** (used for buffering data while sending/receiving)

03:36 — DRAM contents are lost when the router is powered off.  
03:41 — The output lists the **number and type of interfaces** (example: **2 Gigabit Ethernet** and **2 Serial** interfaces).  
03:51 — The output shows about **32 MB of NVRAM**, used to store the **startup configuration** (saved configuration) and **configuration register** settings.  
04:12 — NVRAM contents are preserved when the router is powered off.  
04:16 — The output shows the router has about **4 GB** of physical memory (the total DRAM capacity discussed above).  
04:30 — The output shows about **3 GB of flash**, used to store the IOS image and other system files.  
04:40 — The output shows the **configuration register** value in hex. This reflects the factory-default boot behavior (load IOS from flash, then load startup config from NVRAM).  
04:56 — In authorized password-recovery scenarios, the configuration register can be changed to alter boot behavior so the startup config is not loaded at boot (allowing access without using the usual password).  
05:14 — Summary: `show version` provides key router facts such as **IOS version**, **uptime**, and **memory/storage details**, which is useful for troubleshooting and IOS upgrades.

---

## 17.6 Troubleshooting Methodologies

## 17.6.1 Basic Troubleshooting Approaches

Troubleshooting is an important part of networking. Problems can be simple or complex and may be caused by a mix of **hardware**, **software**, and **connectivity** issues. Technicians should determine the cause of an error before attempting to resolve it.

A common and efficient troubleshooting methodology is based on the **scientific method**.

### Six-step troubleshooting process

| Step | Description |
|---|---|
| **Step 1. Identify the Problem** | - First step in the troubleshooting process. <br> - Tools can help, but talking with the user is often very helpful. |
| **Step 2. Establish a Theory of Probable Causes** | - After identifying the problem, form a theory of probable causes. <br> - Often produces more than a few likely causes. |
| **Step 3. Test the Theory to Determine Cause** | - Test the theories to determine which one is the real cause. <br> - Often a quick procedure is tried first to see if it solves the issue. <br> - If that doesn’t fix it, more research may be needed to find the exact cause. |
| **Step 4. Establish a Plan of Action and Implement the Solution** | After determining the exact cause, create a plan to resolve it and implement the solution. |
| **Step 5. Verify Solution and Implement Preventive Measures** | - After correcting the problem, verify full functionality. <br> - If applicable, implement preventive measures. |
| **Step 6. Document Findings, Actions, and Outcomes** | - Document your findings, actions, and outcomes. <br> - Important for future reference. |

To assess a problem, determine how many devices are affected:
- If only **one device** has the issue, start troubleshooting at that device.
- If **all devices** have the issue, start at the device where all other devices connect.
- Use a consistent method and eliminate **one potential problem at a time**.

---

## 17.6.2 Resolve or Escalate?

Sometimes it is not possible to resolve a problem immediately. A problem should be **escalated** when it requires:
- A **manager decision**
- Specific **expertise**
- A **network access level** the troubleshooting technician does not have

Example: if troubleshooting concludes a router module must be replaced, this should be escalated for **manager approval**. The manager may need to escalate again if a purchase requires approval from the **finance department**.

A company policy should clearly define **when** and **how** a technician escalates a problem.

---

## 17.6.3 The **debug** Command

Operating system processes, protocols, mechanisms, and events generate messages that communicate status. These messages can be valuable during troubleshooting and verification.

The IOS `debug` command:
- Displays real-time messages for analysis
- Must be used carefully (debug output can be high priority and can make the system unusable)
- Should be used only for troubleshooting specific problems
- Can be narrowed to only the relevant feature/subfeature

### Example: `debug ip icmp`

```text
R1# debug ip icmp
ICMP packet debugging is on
R1#
R1# ping 10.1.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms
R1#
*Aug 20 14:18:59.605: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.606: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.608: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.609: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.611: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
R1#
```

To list a short description of all debug command options, use:

```text
debug ?
```

To turn off a specific debug feature, add `no` in front of the debug command:

```text
Router# no debug ip icmp
```

Alternatively, you can use the `undebug` form:

```text
Router# undebug ip icmp
```

To turn off all active debug commands at once:

```text
Router# undebug all
```

**Caution:** Commands such as `debug all` and `debug ip packet` can generate a large amount of output and consume significant resources. A router can become so busy displaying debug output that it may not have enough processing power for normal network functions (or even to accept commands to turn debugging off). These options should be avoided unless absolutely necessary.

---

## 17.6.4 The **terminal monitor** Command

Connections to the IOS CLI can be established in two ways:
- **Locally** — console connection (requires physical access and a rollover cable)
- **Remotely** — Telnet or SSH to an IP-configured device

Some IOS messages (including debug output) are automatically displayed on a **console** connection but not on a **remote** connection. Debug output is not automatically displayed on remote connections because log messages are prevented from being displayed on **vty** lines.

### Example: remote session without terminal monitor

```text
R2# telnet 209.165.200.225
Trying 209.165.200.225 ... Open
Authorized access only!
User Access Verification

Password:
R1> enable
Password:
R1# debug ip icmp
ICMP packet debugging is on
R1# ping 10.1.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms
R1#
< No debug output displayed>
```

To display log messages on a terminal (virtual console), use the privileged EXEC command:

```text
terminal monitor
```

To stop displaying log messages on a terminal:

```text
terminal no monitor
```

### Example: enabling terminal monitor so debug output appears

```text
R1# terminal monitor
R1# ping 10.1.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms
R1#
*Aug 20 16:03:49.735: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 16:03:49.737: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 16:03:49.738: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 16:03:49.740: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 16:03:49.741: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
R1# no debug ip icmp
ICMP packet debugging is off
R1#
```

> **Note:** The intent of `debug` is to capture live output for a short time (seconds to a minute). Always disable debugging when it is no longer needed.


---


# CCNA 1 (ITN) — Module 17: Build a Small Network  
## Part 12 — Troubleshooting: Check Your Understanding + Scenarios (17.6.5–17.7.4)

### Sections in this file
- **17.6.5** Check Your Understanding — Troubleshooting Methodologies  
- **17.7** Troubleshooting Scenarios  
  - **17.7.1** Duplex Operation and Mismatch Issues  
  - **17.7.2** IP Addressing Issues on IOS Devices  
  - **17.7.3** IP Addressing Issues on End Devices  
  - **17.7.4** Default Gateway Issues  

---

## 17.6.5 Check Your Understanding — Troubleshooting Methodologies

### Question 1
A technician is troubleshooting a network problem and has **just established a theory of probable causes**. What should be the **next** step in the troubleshooting process?

✅ **Answer:** **Test the theory to determine cause**  
**Why:** In the common 6‑step troubleshooting model, once you have a theory, you test it (often starting with the easiest/quickest test).

---

### Question 2
After troubleshooting, a technician concludes that a **switch should be replaced**. What should the technician do next?

✅ **Answer:** **Escalate the trouble ticket to the manager to approve the change**  
**Why:** Hardware replacement typically requires approval (budget/change control). If the fix requires management or specialized approval, the issue should be escalated.

---

### Question 3 (Choose two)
A technician is using the `debug ip icmp` privileged EXEC command to capture live router output. Which commands would **stop** this debug command on a Cisco router?

✅ **Answers (choose two):**
- `no debug ip icmp`
- `undebug all`

**Why:**  
- `no debug ip icmp` disables that specific debug feature.  
- `undebug all` turns off all active debugs in one shot.

---

### Question 4
A technician has established a **remote connection** to router R1 to observe debug output. The technician enters `debug ip icmp` and then pings a remote destination, but **no output** is displayed. Which command must the technician enter to display log messages on a remote connection?

✅ **Answer:** `terminal monitor`  
**Why:** Debug output is shown by default on the console, but not automatically on VTY (remote) lines unless terminal monitoring is enabled.

---

## 17.7 Troubleshooting Scenarios

This topic reviews common network issues you are likely to encounter as a network administrator, now that you have basic tools and a troubleshooting process.

---

## 17.7.1 Duplex Operation and Mismatch Issues

In data communications, **duplex** describes the direction of data transmission between two devices.

### Duplex communication modes
- **Half‑duplex** — devices can **send OR receive**, but not at the same time.  
- **Full‑duplex** — devices can **send AND receive simultaneously**.

### Why duplex matters
Interconnecting Ethernet interfaces should operate in the **same duplex mode** for best performance. If they do not, the link can still pass traffic, but it may show:
- poor throughput
- higher latency
- excessive errors/collisions (depending on the media/technology)

### Autonegotiation
Ethernet **autonegotiation** helps avoid duplex problems by having both ends:
1) advertise supported capabilities  
2) agree on the **best** common mode supported by both

### Duplex mismatch
A **duplex mismatch** occurs when one end is full‑duplex and the other end is half‑duplex.

Key points:
- Communication can still happen, which makes the issue tricky to spot.
- Performance is usually **very poor**.

Common causes:
- misconfigured interface settings (most common)
- failed autonegotiation (rare)

---

## 17.7.2 IP Addressing Issues on IOS Devices

Incorrect IP addressing can prevent devices from communicating across the network.

### Why wrong addressing breaks communication
Because IP addresses are **hierarchical**, any IP address assigned to a device interface must match the addressing plan for that network. Wrong IP settings can cause:
- **IP address conflicts**
- routing failures / unreachable networks
- inability to reach remote devices

### Common causes
- **manual assignment mistakes** (common on routers/servers)
- **DHCP‑related issues** (when automatic addressing is used)

### Verify interface addressing on IOS
On Cisco IOS devices, verify addressing and interface status using:
- `show ip interface`
- `show ip interface brief`

Example `show ip interface brief` output (router):

```text
R1# show ip interface brief
Interface              IP-Address        OK? Method Status                Protocol
GigabitEthernet0/0/0    209.165.200.225   YES manual up                    up
GigabitEthernet0/0/1    192.168.10.1      YES manual up                    up
Serial0/1/0             unassigned        NO  unset  down                  down
Serial0/1/1             unassigned        NO  unset  down                  down
GigabitEthernet0        unassigned        YES unset  administratively down  down
```

What to look for:
- correct **IP address** and **subnet**
- interface **Status/Protocol** (up/up is expected for active links)
- unexpected **unassigned** addresses where addressing is required

---

## 17.7.3 IP Addressing Issues on End Devices

### APIPA on Windows
On Windows devices, if the host cannot contact a DHCP server, Windows may automatically assign an address from **169.254.0.0/16**. This feature is called:

- **APIPA (Automatic Private IP Addressing)**

APIPA is meant to allow limited local communication, but in most enterprise LANs it indicates a problem because other devices are usually not using 169.254.0.0/16.

### What an APIPA address usually means
- the end device could not get a DHCP lease
- the host will likely fail to reach most network resources (wrong subnet for that LAN)

> Note: Other operating systems (e.g., Linux, macOS) commonly do **not** assign an IPv4 address to the interface if DHCP fails.

### Verify end-device addressing
On Windows, use `ipconfig` to verify address information (example):

```text
C:\Users\PC-A> ipconfig
Windows IP Configuration

Wireless LAN adapter Wi-Fi:
   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::a4aa:2dd1:ae2d:a75e%16
   IPv4 Address. . . . . . . . . . . : 192.168.10.10
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : 192.168.10.1
```

---

## 17.7.4 Default Gateway Issues

The **default gateway** is the closest networking device that forwards traffic to other networks (typically a router interface on the local LAN).

### Symptoms of wrong/missing default gateway
If an end device has an incorrect or missing default gateway, it can usually:
- communicate on the **local network**
- but **cannot reach remote networks**

### Gateway must be in the same network
Because the default gateway is the path out of the local network, its IP address must be in the **same subnet** as the end device.

### Causes
- manual configuration error (wrong gateway typed in)
- DHCP issues (device cannot reach DHCP server or DHCP is misconfigured)

### Fix approach
- If manually set: replace it with the correct gateway address.
- If DHCP-provided: verify the device can reach DHCP and that the DHCP scope/options are correct.
- Also verify the router’s interface for that LAN has the correct IP/subnet and is operational.

### Verify the default gateway on Windows
Use `ipconfig` and confirm the **Default Gateway** value (example):

```text
Default Gateway . . . . . . . . . : 192.168.10.1
```

### Verify the default gateway/default route on a router
On a router, use `show ip route` to confirm a default route (gateway of last resort) exists.

Example snippet:

```text
R1# show ip route | begin Gateway
Gateway of last resort is 209.165.200.226 to network 0.0.0.0

O*E2 0.0.0.0/0 [110/1] via 209.165.200.226, 02:19:50, GigabitEthernet0/0/0
```

What this tells you:
- the router has a **default route** pointing to the next hop (**209.165.200.226**)
- traffic for unknown destinations can be forwarded out the correct interface

---
