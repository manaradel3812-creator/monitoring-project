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

## 🖼️ Screenshots

<img width="1600" height="808" alt="image" src="https://github.com/user-attachments/assets/bd399c4c-a8a8-4444-ac7d-750ffc00280d" />

<img width="1600" height="801" alt="image" src="https://github.com/user-attachments/assets/fad5b435-3b56-499c-b11f-ae7b03ff9947" />

<img width="1600" height="696" alt="image" src="https://github.com/user-attachments/assets/17a493be-9320-446a-b867-dc4630806866" />
<img width="1600" height="801" alt="image" src="https://github.com/user-attachments/assets/b9c034a3-ea26-483b-a549-362798b82e55" />
<img width="1460" height="664" alt="image" src="https://github.com/user-attachments/assets/33bca1e9-8c0f-423c-9fbb-f8da9dac1d0f" />

<img src="images/prometheus1.png" alt="Prometheus" width="600"/>
<img src="images/grafana1.png" alt="Grafana" width="600"/>
<img src="images/alertmanager1.png" alt="Alertmanager" width="600"/>
<img src="images/nodeexporter1.png" alt="Node Exporter" width="600"/>
<img src="images/stack_overview.png" alt="Stack Overview" width="600"/>
