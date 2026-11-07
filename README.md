# Hi, I'm Bezhan 👋

### Network & Platform Engineer
**ISP Infrastructure · Linux · Automation · Observability**

I design, operate, troubleshoot, and automate infrastructure for internet service providers. My work sits at the intersection of **network engineering, Linux platforms, and practical software development** — from DNS and virtualization to monitoring and end-to-end operational workflows.

> If a team has to repeat the same manual workflow every day, I look for a way to engineer it out.

---

## ☁️ Featured infrastructure case — Production Private Cloud & DNS

### [OpenStack Kolla-Ansible Multinode → Proxmox VE | Carrier-Grade DNS](projects/private-cloud-dns-observability.md)

Designed and deployed a **production multinode OpenStack private cloud**, launched **two Unbound DNS resolvers** for a mobile network operator serving **~100,000 subscribers**, built the monitoring and alerting stack, and subsequently migrated the DNS infrastructure to **Proxmox VE**.

- **Cloud/platform:** OpenStack (Kolla-Ansible Multinode), virtual networking, segmentation, firewall policy, Proxmox VE migration.
- **DNS operations:** Unbound DNS1/DNS2, resolver performance analysis, availability monitoring.
- **Observability:** custom Prometheus DNS exporter, Grafana dashboards for QPS, cache efficiency, NXDOMAIN/SERVFAIL, latency, infrastructure health, and alert rules.
- **NOC automation:** [dns-noc-bot](https://github.com/codexhtb/dns-noc-bot), a Python Telegram tool for Prometheus-powered status, alert, conntrack, comparison and graph commands.

**Observed Grafana snapshot:** **4.18B DNS queries · 4.02B cache hits · 96.2% cache hit ratio** (cumulative counters and point-in-time ratio, not an SLA or annual benchmark).

**[Read the architecture, migration and observability case study →](projects/private-cloud-dns-observability.md)**

---

## 📰 Featured engineering postmortem — published on Habr

### [Reviving Huawei SANEX9510: expired certificates, an empty keystore, and a missing `@`](https://habr.com/ru/articles/1101712/)

**[Read the original article on Habr (Russian) →](https://habr.com/ru/articles/1101712/)**

A real telecom OSS recovery investigation: **seven distinct failure modes** across legacy TLS/PKI, PKCS#12 and PKCS#8 compatibility, Java keystores, and Sybase IQ connections. I reconstructed component dependencies and helped restore the system over **three days**, without rebooting the database. The article walks through diagnosis, misleading symptoms, safe recovery decisions, and lessons for observability.

**Skills demonstrated:** incident response · root-cause analysis · Linux · PKI/TLS · legacy systems · production troubleshooting

---

## 🚀 Featured projects

### [OSS Control Center](https://github.com/codexhtb/oss-control-center) — ISP Operations Platform

**The problem:** Support operators and network engineers had to switch between a legacy service desk, billing, monitoring, network CLI, and messengers to resolve a single subscriber issue.

**The solution:** An integrated internal platform built around the actual ISP support workflow:

- Subscriber lookup and service context from **NetUP UTM5** through a read-only data path.
- Tickets, operator/engineer queues, resolution history, and customer follow-up.
- **LibreNMS / BDCOM EPON–GPON** diagnostics linked to subscriber connections, including ONU status and disconnection reasons.
- Structured field dispatch via **Telegram bot**, with feedback returned to the ticket workflow.
- Internal team chat to reduce fragmented operational communication.

**Stack:** Python · FastAPI · React · TypeScript · PostgreSQL · Docker · MariaDB · LibreNMS · NetUP

**My focus:** Workflow design, infrastructure, data integration, technical decision-making, and validating the system against real network operations.

### [CLIRace](https://github.com/codexhtb/clirace) — Hands-on Linux & DevOps Learning

A practice and competition platform where users solve real Linux tasks in isolated shell environments rather than only answering quizzes.

- Disposable **rootless Docker** sandboxes with resource and network isolation.
- Browser terminal and real-time multiplayer interactions over **WebSocket**.
- Linux learning paths, practical labs, challenges, rankings, and interview preparation.
- Backend-managed sessions, progress tracking, and operational controls.

**Stack:** TypeScript · Fastify · React · PostgreSQL · Redis · Docker · WebSocket

### [Pulse](https://github.com/codexhtb/pulse) — DNS Observability for Unbound

A self-hosted platform for understanding what DNS resolvers are doing in real time, without placing the monitoring system in the critical DNS request path.

- **DNStap** ingestion and query/response correlation, including unmatched or missing responses.
- **ClickHouse** storage and aggregations for DNS traffic, RCODEs, QPS, and latency percentiles.
- Live traffic and operational dashboards via **REST / Server-Sent Events**.
- Optional isolated DNS control-plane components.

**Stack:** Go · Unbound · DNStap · ClickHouse · React · Docker

---

## 🛠️ Infrastructure & incident engineering

- **Cloud and DNS infrastructure:** Production deployment of **OpenStack / Kolla-Ansible Multinode**, Unbound DNS services and a later **Proxmox VE** migration — [full engineering case study](projects/private-cloud-dns-observability.md).
- **Network observability:** Modernized monitoring with **LibreNMS**, **Icinga 2**, SNMP-based discovery, PON telemetry, and automated configuration backups.
- **Linux networking:** Investigated conntrack pressure during network events, adjusted Netfilter capacity, and diagnosed multi-interface **ARP flux** incidents.
- **Huawei SANEX9510 recovery:** Investigated a complex telecom OSS outage involving legacy PKI/TLS, Java keystores and database connections — [technical postmortem on Habr](https://habr.com/ru/articles/1101712/).

These examples are intentionally high-level: internal topology, credentials, subscriber data, and sensitive production configuration are not part of this public profile.

## ⚙️ Technologies I work with

| Area | Tools & technologies |
| --- | --- |
| **Network engineering** | TCP/IP, VLANs, routing, BGP/OSPF, DNS, SNMP, Cisco, BDCOM EPON/GPON |
| **Platforms & virtualization** | Linux, Proxmox VE, KVM, OpenStack (Kolla-Ansible), Docker, Kubernetes |
| **Observability** | LibreNMS, Icinga 2, Prometheus, Grafana, Loki, DNStap |
| **Software & data** | Python, Go, TypeScript, Bash, FastAPI, React, PostgreSQL, MariaDB, ClickHouse, Redis |
| **Operations** | Git, GitHub, Docker Compose, troubleshooting, backup/recovery, infrastructure documentation |

---

### Engineering philosophy

**Understand the failure mode. Design for recovery. Automate the repetitive parts. Keep the operational path simple.**

Explore the repositories above for implementation details, architecture diagrams, and technical documentation.
