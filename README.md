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
