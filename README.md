**🌐 Language:** **English** · [Русский](README.ru.md)

---

# Hi, I'm Bezhan 👋

**Network & Platform Engineer**  
ISP Infrastructure · Private Cloud · Linux · Automation · Observability

I build and operate infrastructure for internet service providers — from virtualization and DNS to monitoring, incident response, and tools that remove repetitive operational work.

## Selected work

### ☁️ [Production Private Cloud & DNS Infrastructure](projects/private-cloud-dns-observability.md)

Deployed **OpenStack with Kolla-Ansible Multinode** in production, running two **Unbound DNS resolvers** for a mobile network operator with approximately **100,000 subscribers**. Built the network foundation, custom Prometheus metrics, Grafana dashboards, and alerting. Later migrated the DNS workloads to **Proxmox VE**.

**Grafana snapshot:** 4.18B DNS queries · 4.02B cache hits · 96.2% cache hit ratio (point-in-time/cumulative dashboard readings).

Also built [**dns-noc-bot**](https://github.com/codexhtb/dns-noc-bot) — a Telegram interface for Prometheus-powered DNS health checks, alerts, conntrack, and traffic graphs.

### 🛠️ [OSS Control Center](https://github.com/codexhtb/oss-control-center)

An internal ISP operations platform connecting **NetUP UTM5**, **LibreNMS/BDCOM**, ticket management, subscriber diagnostics, field dispatch, customer callbacks, and team chat. Designed to replace repetitive lookups and fragmented support workflows.

[Architecture & engineering case study](https://github.com/codexhtb/oss-control-center/blob/main/docs/portfolio-case-study.md) · **FastAPI · React · TypeScript · PostgreSQL · Docker**

### 📰 [Huawei SANEX9510 — Production Incident Postmortem](https://habr.com/ru/articles/1101712/)

Published a technical investigation on **Habr** (in Russian) covering a complex telecom OSS outage, legacy TLS/PKI, Java keystores, and database connectivity. A practical case in root-cause analysis and recovery of a critical system.

### 💻 [CLIRace](https://github.com/codexhtb/clirace)

A hands-on Linux and DevOps learning platform with real terminal sessions in **isolated rootless Docker containers**, challenges, and multiplayer interactions.

**TypeScript · Fastify · React · PostgreSQL · Redis · WebSocket**

### 📡 [Pulse — DNS Observability](https://github.com/codexhtb/pulse)

A self-hosted observability platform for **Unbound**, using **DNStap**, a **Go** collector, **ClickHouse**, and a real-time web interface for DNS transaction correlation, traffic analysis, and latency investigation.

## Operations & documentation

- Maintain internal infrastructure documentation and recovery runbooks in **BookStack**; write incident postmortems after outages.
- Work with production **Linux networking**, including conntrack capacity, ARP issues, network monitoring, and troubleshooting.
- Build monitoring for network devices and EPON/GPON access infrastructure using **LibreNMS**, **Icinga 2**, SNMP, and configuration backups.

## Core technologies

**Platforms:** Linux · OpenStack · Kolla-Ansible · Proxmox VE · KVM · Docker  
**Networking:** TCP/IP · BGP/OSPF · VLANs · DNS · Unbound · Cisco · BDCOM EPON/GPON  
**Observability:** Prometheus · Grafana · LibreNMS · Icinga 2 · ClickHouse · DNStap  
