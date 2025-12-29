# 🚀 Monitoring Stack Project

![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)
![Podman](https://img.shields.io/badge/Podman-F5533D?style=for-the-badge&logo=podman&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

This project demonstrates how to *set up a centralized monitoring stack* using *Ansible* and *Podman*, providing an interactive dashboard for system metrics and alert management.

---

## 🗂️ Project Overview

The monitoring stack includes multiple components:

- *Prometheus* 🟢 – Collects and stores metrics.  
- *Grafana* 📊 – Visualizes metrics with interactive dashboards.  
- *Alertmanager* ⚠️ – Handles system alerts.  
- *Node Exporter* 💻 – Exports host hardware and OS metrics to Prometheus.  

Organized using *Ansible roles*, the deployment is automated and modular for easy management.

---

## 🗂️ Project Structure

monitoring-project/
├── ansible.cfg
├── inventory/
│   └── hosts       # Define connection to localhost
├── playbooks/
│   ├── monitoring-stack.yml   # Deploys Prometheus, Grafana, Alertmanager
│   └── node-exporter.yml      # Deploys Node Exporter
└── roles/                     # Contains individual tasks and config files

## ⚙️ Prerequisites

Before running the playbooks, ensure you have:

- A Linux VM (Ubuntu/Debian recommended) 🐧  
- Python 3 and Ansible installed 🐍  
- Podman installed 🐳  
- Sudo privileges to manage containers 🔑  

---

## 🛠️ Deployment Steps

1. *Create the monitoring network*:  
```bash
sudo podman network create monitoring_net
---

2. **Upload all screenshots** into `images/` folder:

##🖼️ Screenshots
![Prometheus Dashboard](images/prometheus1.png)
![Grafana Dashboard](images/grafana1.png)
![Alertmanager](images/alertmanager1.png)
![Node Exporter Metrics](images/nodeexporter1.png)
![Complete Stack Overview](images/stack_overview.png)


<img src="images/prometheus1.png" alt="Prometheus Dashboard" width="600"/>
<img src="images/grafana1.png" alt="Grafana Dashboard" width="600"/>
<img src="images/alertmanager1.png" alt="Alertmanager" width="600"/>
<img src="images/nodeexporter1.png" alt="Node Exporter Metrics" width="600"/>
<img src="images/stack_overview.png" alt="Complete Stack Overview" width="600"/>


