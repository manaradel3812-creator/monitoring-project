# Monitoring Stack Project

This project sets up a **centralized monitoring stack** using **Ansible** and **Podman**.  
It includes the following components:

- **Prometheus**: Collects and stores metrics
- **Grafana**: Visualizes metrics with dashboards
- **Alertmanager**: Handles alerts
- **Node Exporter**: Exports host metrics to Prometheus

---

## Features

- Fully automated deployment with **Ansible playbooks**
- Containerized services using **Podman**
- Monitoring of the local host
- Easy access to web UIs for each service

---

## Requirements

- Linux VM (Ubuntu/Debian recommended)
- Python 3
- Ansible installed
- Podman installed
- Sudo privileges (recommended)

---

## Project Structure

monitoring-project/
├── ansible.cfg
├── inventory/
│ └── hosts
├── playbooks/
│ ├── monitoring-stack.yml # Deploy Prometheus, Grafana, Alertmanager
│ └── node-exporter.yml # Deploy Node Exporter on host
└── roles/
├── prometheus/
│ ├── files/prometheus.yml
│ └── tasks/main.yml
├── alertmanager/
│ ├── files/alertmanager.yml
│ └── tasks/main.yml
├── grafana/
│ └── tasks/main.yml
└── node_exporter/
├── files/
└── tasks/main.yml


---

## Inventory Example

`inventory/hosts`:

```ini
[monitoring]
localhost ansible_connection=local

The playbooks will run on the localhost.

Deployment
1. Ensure network exists
sudo podman network create monitoring_net

2. Deploy Centralized Monitoring Stack
ansible-playbook playbooks/monitoring-stack.yml --ask-become-pass

3. Deploy Node Exporter
ansible-playbook playbooks/node-exporter.yml --ask-become-pass

Access Services

Prometheus → http://localhost:9090

Alertmanager → http://localhost:9093

Grafana → http://localhost:3000

Default login: admin / admin

Node Exporter metrics are available for Prometheus on port 9100.

Notes

If you want to run the playbooks without sudo:

Remove become: true from the playbooks

Change file permissions to allow read access:

chmod 644 roles/prometheus/files/prometheus.yml
chmod 644 roles/alertmanager/files/alertmanager.yml


All containers are connected via Podman network monitoring_net.

License

This project is open-source. You can add a license of your choice (e.g., MIT License).








 







