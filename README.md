
--------------------------------------------------------------------------------
Monitoring Stack Project
This project sets up a centralized monitoring stack using Ansible and Podman. It is designed to monitor the local host and provide a visual dashboard for system metrics.
Components
• Prometheus: Collects and stores metrics.
• Grafana: Visualizes metrics with interactive dashboards.
• Alertmanager: Handles and manages system alerts.
• Node Exporter: Exports host hardware and OS metrics to Prometheus.
Project Structure
Organizing the project into Ansible Roles allows for better management:
monitoring-project/
├── ansible.cfg
├── inventory/
│   └── hosts            # Define connection to localhost
├── playbooks/
│   ├── monitoring-stack.yml # Deploys Prometheus, Grafana, Alertmanager
│   └── node-exporter.yml    # Deploys Node Exporter
└── roles/               # Contains individual tasks and config files
Prerequisites
Before running the playbooks, ensure you have:
• A Linux VM (Ubuntu/Debian recommended).
• Python 3 and Ansible installed.
• Podman installed.
• Sudo privileges to manage containers.
Deployment Steps
To get the system running, execute these commands in order:
1. Create the monitoring network: sudo podman network create monitoring_net
2. Deploy the Centralized Stack: ansible-playbook playbooks/monitoring-stack.yml --ask-become-pass
3. Deploy Node Exporter: ansible-playbook playbooks/node-exporter.yml --ask-become-pass
Accessing the Services
Once deployed, you can access the web interfaces at these addresses:
• Prometheus: http://localhost:9090
• Alertmanager: http://localhost:9093
• Grafana: http://localhost:3000 (Default login: admin / admin)

--------------------------------------------------------------------------------
