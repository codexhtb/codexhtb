# Production Private Cloud & Carrier-Grade DNS

**OpenStack (Kolla-Ansible Multinode) → Proxmox VE · Unbound · Prometheus · Grafana · NOC Automation**

[← GitHub profile](../README.md) · [DNS NOC Bot](https://github.com/codexhtb/dns-noc-bot) · [Pulse: DNS Observability](https://github.com/codexhtb/pulse)

> **Role:** Network / Platform Engineer — deployment, architecture, networking, DNS infrastructure, monitoring, automation, and migration.  
> **Environment:** Production infrastructure for a mobile network operator with approximately **100,000 subscribers**. This is the approximate operator subscriber base, **not** the number of concurrent DNS clients.  
> **Publishing scope:** High-level technical case study. Exact topology, node identities, management addresses, secrets, and internal alert destinations are intentionally omitted.

## Executive overview

I deployed a **multinode OpenStack private-cloud environment with Kolla-Ansible** for production use, provisioned and operated **two Unbound DNS resolvers**, and implemented the observability and operational tooling around them. The DNS infrastructure was subsequently **migrated from OpenStack to Proxmox VE**.

This was an end-to-end infrastructure project: virtualization and network design, DNS service configuration, custom metric collection, Prometheus, Grafana dashboards, alerting, and a Telegram-based NOC utility.

## Delivery timeline

| Stage | What I engineered |
| --- | --- |
| **1 — Private cloud** | Production OpenStack multinode deployment using Kolla-Ansible; host and virtual network integration |
| **2 — DNS services** | Two Unbound resolver VMs for operator DNS workloads; deployment and service tuning |
| **3 — Network foundation** | Segmentation, firewall rules and controlled communication between infrastructure components |
| **4 — Observability** | Custom DNS metrics exporter, Prometheus collection, Grafana visualizations and essential alerts |
| **5 — Operations automation** | Python Telegram NOC bot querying Prometheus for current health, performance and alerts |
| **6 — Platform migration** | Migration of the DNS workloads from OpenStack to **Proxmox VE** for their subsequent operational environment |

The exact cutover procedure, downtime/RTO/RPO, number of OpenStack nodes, and performance before vs. after migration are not asserted here without deployment records.

## Architectural view

The diagram is **conceptual**; it shows the two platform stages and monitoring relationships, not actual L2/L3 topology or a live side-by-side deployment.

~~~mermaid
flowchart TB
    subgraph STAGE1["Stage 1 — Production private cloud"]
      OS["OpenStack · Kolla-Ansible Multinode"]
      OS --> V1["Unbound DNS1 VM"]
      OS --> V2["Unbound DNS2 VM"]
    end
    subgraph STAGE2["Stage 2 — After migration"]
      PVE["Proxmox VE"]
      PVE --> N1["Unbound DNS1 VM"]
      PVE --> N2["Unbound DNS2 VM"]
    end
    OS -. "workload migration" .-> PVE
    subgraph OBS["Observability and operations"]
      EXP["Custom DNS exporter / node metrics"]
      PROM["Prometheus"]
      GRAF["Grafana dashboards"]
      ALERT["Alert rules"]
      NOC["dns-noc-bot · Telegram"]
      EXP --> PROM
      PROM --> GRAF
      PROM --> ALERT
      PROM --> NOC
    end
    N1 -. "DNS / node metrics" .-> EXP
    N2 -. "DNS / node metrics" .-> EXP
~~~

> Monitoring components are shown alongside the current platform for readability. Their exact VM placement and deployment chronology are intentionally abstracted.

## Observability I built

The monitoring system combines DNS-specific and host-level telemetry:

- **DNS traffic:** queries per second (QPS), traffic split across resolvers and peak request load.
- **Resolution health:** SERVFAIL, NXDOMAIN and request-rate anomalies.
- **Cache effectiveness:** cache hits/misses, prefetch and cache hit ratio.
- **Performance:** average/median lookup and recursion times.
- **Host reliability:** resource use, uptime and Linux connection tracking capacity.
- **Operational alerting:** alerts for important DNS and infrastructure conditions, with on-call/NOC visibility.

### Representative Grafana snapshot

A supplied operational dashboard snapshot showed:

| Metric | Value shown | Interpretation |
| --- | ---: | --- |
| Total DNS queries | **4,182,539,140** | Accumulated counter on the dashboard |
| Cache hits | **4,022,909,932** | Accumulated cache-hit counter |
| Cache misses | **159,629,208** | Accumulated cache-miss counter |
| Cache hit ratio | **96.2%** | Dashboard metric at the time of capture |
| Resolver uptime | **179 days 11 hours** | Value displayed by the monitored DNS instance |
| DNS resolvers | **2** | Unbound DNS1 and DNS2 |

**Evidence qualification:** these are readings from a screenshot, not an independent benchmark or long-term SLA. Counter lifetimes and dashboard time ranges should be verified before treating totals as annual traffic. The often-quoted **40+ billion** cumulative cache-hit figure is not used here because the supplied screenshot supports **4.02 billion**.

A high hit ratio indicates significant local cache serving; it does **not** by itself quantify upstream bandwidth savings or causally prove improved latency. Those would require measured before/after baselines.

## DNS NOC Bot

[**View source → dns-noc-bot**](https://github.com/codexhtb/dns-noc-bot)

I developed a lightweight **Python Telegram operational interface** to Prometheus so that day-to-day DNS checks do not require opening Grafana for every question.

The repository implements commands for:

| Command / capability | Purpose |
| --- | --- |
| \`/status\` | Per-resolver QPS, recent peak, CPU, free RAM, cache, failures and conntrack |
| \`/health\` | Overview of monitored resolvers and an indicative traffic split |
| \`/alerts\` | Current firing Prometheus alerts |
| \`/compare\`, \`/summary\` | Compare DNS traffic and summarize NOC health |
| \`/graph\`, \`/overlay\` | Generate DNS QPS plots using Prometheus range queries |
| \`/conntrack\` | Inspect connection-tracking utilization |
| \`/analyze\` | Basic resolver metrics analysis |

The bot illustrates a **pragmatic NOC workflow**, not an autonomous incident-remediation agent. Readiness for unrestricted deployment requires access control, configuration cleanup and least-privilege service operation; the public code should be reviewed before re-use.

## Why this project matters

This work demonstrates the combination of **cloud/platform deployment** and **carrier-grade network operations**:

1. I built and operated an infrastructure platform, not just an application running on someone else's cloud.
2. I connected DNS behavior to operating-system and virtualization metrics.
3. I designed Grafana dashboards around troubleshooting decisions rather than decorative metrics.
4. I automated repeatable NOC checks using the observability API.
5. I later migrated the workloads to another virtualization platform, keeping platform lifecycle and operational needs in view.

## Technical stack

**Cloud & virtualization:** OpenStack, Kolla-Ansible, Proxmox VE, Linux, KVM.  
**Networking:** TCP/IP, VLAN segmentation, firewall policy, service connectivity.  
**DNS:** Unbound, resolver configuration and metrics.  
**Observability:** Prometheus, Grafana, custom DNS exporter, alert rules.  
**Automation:** Python, Telegram Bot API, Prometheus HTTP API, Git.

## Related work

- **[Pulse — DNS Observability Platform](https://github.com/codexhtb/pulse):** a separate Go / DNStap / ClickHouse project for individual DNS transaction correlation, latency, and real-time traffic.
- **[OSS Control Center](https://github.com/codexhtb/oss-control-center):** a separate ISP service desk and network diagnostics integration project.

## Disclosure

No production IPs, credentials, exact network diagram, subscriber data, or internal Grafana screenshots are embedded here. Authorized, anonymized screenshots and independently verified reliability/performance figures can be added later.

---

*Engineering portfolio case study · November 2026*
