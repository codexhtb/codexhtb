# Hi, I'm Bezhan 👋

### Network & Platform Engineer
**ISP Infrastructure · Linux · Automation · Observability**

I design, operate, troubleshoot, and automate infrastructure for internet service providers. My work sits at the intersection of **network engineering, Linux platforms, and practical software development** — from DNS and virtualization to monitoring and end-to-end operational workflows.

> If a team has to repeat the same manual workflow every day, I look for a way to engineer it out.

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

- **Carrier-grade DNS:** Deployed and operated Unbound resolver infrastructure; worked with a multinode **OpenStack / Kolla-Ansible** environment and subsequent migration of core services to **Proxmox VE**.
- **Network observability:** Modernized monitoring with **LibreNMS**, **Icinga 2**, SNMP-based discovery, PON telemetry, and automated configuration backups.
- **Linux networking:** Investigated conntrack pressure during network events, adjusted Netfilter capacity, and diagnosed multi-interface **ARP flux** incidents.
- **Storage incident recovery:** Troubleshot a Huawei SANEX9510 service outage involving PKI/TLS, Java keystores, and certificate handling.

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
