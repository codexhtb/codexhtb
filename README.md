### Hi, my name is Bezhan 👋 

**Infrastructure & Network Engineer** based in Abkhazia. Passionate about building robust carrier-grade telecommunications infrastructure, high-performance virtualization, Linux kernel internals, and automation. 

---

### 🚀 Core Tech Stack

* **Virtualization & Systems:** OpenStack (Kolla Ansible Multinode), Proxmox VE (PVE Cluster), KVM, Kubernetes, Docker / Containerization
* **Networking & Protocols:** TCP/IP, BGP/OSPF, DNS (Unbound, BIND, PowerDNS), Cisco switches & ASA, BDCOM PON
* **Observability & Monitoring:** ClickHouse, Prometheus, Loki, InfluxDB, Grafana (custom production dashboards), LibreNMS, Zabbix
* **Languages & Tooling:** Go (Pulse backend), Python, Bash, Git, LLM Ops / RAG system design (Pytest), Linux Kernel optimization

---

### 💡 Key Projects & Achievements

* **Pulse — DNS Observability Platform:** Developed a high-performance self-hosted DNS observability system for Unbound resolvers using DNStap telemetry, a Go/SSE backend, ClickHouse storage, and a real-time Web UI for transaction tracking, latency percentiles, and anomaly detection[cite: 4].
* **Carrier-Grade DNS & Infrastructure Migration:** Initially deployed and scaled a high-load DNS cluster (Unbound) on a production **OpenStack (Kolla Ansible Multinode)** cluster built from scratch, serving 100k+ subscribers at 4K+ QPS. Successfully engineered the subsequent migration of core services to a high-performance **Proxmox VE** cluster.
* **Huawei SANEX9510 Recovery:** Successfully restored a critical infrastructure outage by deep-diving into PKI/TLS protocols, Java keystores, and encoding debugging where vendor support stalled.
* **CodexOps V1 (NOC AI Assistant):** Built a secure, read-only local LLM/RAG assistant for infrastructure ops backed by 700+ pytest tests and strict RCE boundaries.

---

### 🛠️ Production Troubleshooting & Post-Mortems

* **Netfilter Conntrack Optimization:** Mitigated severe traffic storms caused by regional power-grid outages by tuning kernel parameters, extending `nf_conntrack_max` to 2M, adjusting hash sizes, and overriding `pve-firewall` limits.
* **L2 ARP Flux Resolution:** Diagnosed and resolved complex production outages caused by weak host model ARP conflicts and multi-interface overlapping subnets.

---

### 🎯 Focus
High-load networking, SRE/DevOps automation, Proxmox clustering, and resilient infrastructure design.
