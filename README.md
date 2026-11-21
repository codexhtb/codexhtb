**🌐 Language:** **English** · [Русский](README.ru.md)

---

# Hi, I'm Bezhan 👋

**Network & Platform Engineer**

ISP Infrastructure · Private Cloud · Linux · Automation · Observability

I work in telecommunications, designing, deploying and maintaining network and server infrastructure for internet service providers and mobile network operators.

My responsibilities cover the entire infrastructure lifecycle — from physical servers, networking and virtualization to production operations, observability, automation and incident recovery.

## Engineering expertise

- **Network Engineering** — ISP network infrastructure, network architecture, troubleshooting and production operations.
- **Infrastructure & Platform Engineering** — physical servers, Linux, private clouds, OpenStack, Proxmox VE, virtualization and workload migration.
- **DNS Infrastructure** — deployment, configuration, monitoring and operation of production recursive DNS services.
- **Observability Engineering** — monitoring infrastructure, custom exporters, telemetry collectors, monitoring templates, dashboards and alerting.
- **Databases** — deployment, administration, backup, recovery and integration with infrastructure services.
- **DevOps** — Kubernetes, Terraform, Infrastructure as Code and CI/CD pipelines.
- **Engineering Automation** — development of internal tools and platforms that solve operational problems and automate repetitive engineering tasks.
- **Incident Management** — troubleshooting complex production failures, service recovery, root-cause analysis, incident postmortems and technical documentation.

## Selected engineering projects

### [Production Private Cloud & DNS Infrastructure](projects/private-cloud-dns-observability.md)

Designed and deployed a production multinode OpenStack private cloud using Kolla-Ansible, hosting recursive DNS infrastructure for a mobile network operator serving approximately 100,000 subscribers.

My work included infrastructure deployment, network integration, Unbound resolver configuration, custom metrics collection, Prometheus, Grafana dashboards and alerting.

Later migrated the DNS workloads from OpenStack to Proxmox VE.

**Technologies:** OpenStack · Kolla-Ansible · Proxmox VE · Linux · Unbound · Prometheus · Grafana

### [OSS Control Center](https://github.com/codexhtb/oss-control-center)

An internal operations platform for internet service providers, developed to consolidate technical support, network diagnostics and engineering workflows.

The project covers the entire solution, from physical server preparation, virtualization, database infrastructure and monitoring deployment to application architecture and development.

The platform integrates NetUP UTM5, LibreNMS, subscriber diagnostics, EPON/GPON equipment monitoring, ticket management, field operations, customer callbacks and internal team communication.

[Architecture & engineering case study](https://github.com/codexhtb/oss-control-center/blob/main/docs/portfolio-case-study.md)

**Technologies:** Linux · Proxmox VE · FastAPI · React · TypeScript · PostgreSQL · MariaDB · Docker · LibreNMS

### [Pulse — DNS Observability](https://github.com/codexhtb/pulse)

A self-hosted DNS observability platform designed for Unbound infrastructure.

Pulse provides transaction-level visibility into DNS traffic through DNStap telemetry, a Go-based collection and correlation pipeline, persistent correlation state and ClickHouse storage.

Features include real-time DNS traffic analysis, query-response correlation, latency investigation, resolver comparison, anomaly detection and an independent DNS control plane.

The platform operates outside the critical DNS resolution path.

**Technologies:** Go · DNStap · ClickHouse · Unbound · React · TypeScript · Docker

### [DNS NOC Bot](https://github.com/codexhtb/dns-noc-bot)

An operational Telegram interface for production DNS infrastructure, integrating with Prometheus to provide resolver health checks, traffic analysis, performance metrics, active alerts and Linux connection-tracking statistics.

**Technologies:** Python · Prometheus · Telegram Bot API · Linux

### [CLIRace](https://github.com/codexhtb/clirace)

An interactive Linux and DevOps learning platform featuring real terminal environments, practical challenges and multiplayer sessions running in isolated rootless Docker containers.

**Technologies:** TypeScript · Fastify · React · PostgreSQL · Redis · Docker · WebSocket

## Incident investigations & technical writing

### [Huawei SANEX9510 — Production Incident Postmortem](https://habr.com/ru/articles/1101712/)

A published technical investigation covering the recovery of a critical telecommunications OSS platform after ten months of downtime.

Identified and resolved seven independent failures across multiple service dependencies, including legacy TLS/PKI, Java keystores, cryptographic compatibility and Sybase IQ database connectivity.

Restored the system within three days without rebooting the servers or restarting the database.

Published on Habr (in Russian).

In addition to public technical writing, I maintain internal infrastructure documentation, operational procedures, recovery runbooks and incident postmortems for critical production systems using BookStack.
