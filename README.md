# 8.7/10 Enterprise Home Data Center

Documentation for my 3-node Proxmox cluster + IBM Power lab.

**Live metrics & diagram:** https://sushenjayasuriya.org.lk/lab

### Architecture
- **sliit-pve:** Dell R320 32GB — Proxmox VE — 12+ VMs/LXCs
- **pbs-backup:** Dell R310 — Proxmox Backup Server — 7/4/3 retention  
- **pfsense-fw:** Dell R210 II — pfSense — VLANs, WireGuard, Suricata
- **ibm-power:** IBM Power 550 — AIX LPARs + VIOS
- **Storage:** IBM SAN + LTO Tape Library

### Key Files
- `lab-diagram.drawio` — Full network topology with VLANs + IPs
- `proxmox/` — VM configs, storage.cfg, network configs
- `pfsense/` — Firewall rules, VLAN setup, HAProxy config
- `monitoring/` — Grafana dashboards, Prometheus alerts
- `dr-procedure.md` — Quarterly <15min RTO test procedure

### Disaster Recovery Test Results
| Date | RTO | RPO | Method |
| --- | --- | --- | --- |
| 2026-01-15 | 12min | <1hr | LTO tape → PBS → PVE |
| 2025-10-20 | 14min | <1hr | LTO tape → PBS → PVE |

**This lab simulates enterprise environments I want to manage at scale.**
