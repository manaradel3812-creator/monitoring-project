<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Monitoring Stack Project</title>
</head>
<body>
    <h1>🖥️ Monitoring Stack Project</h1>
    <p>This project sets up a <strong>centralized monitoring stack</strong> using <strong>Ansible</strong> and <strong>Podman</strong>. It allows you to monitor your local host and visualize system metrics through a user-friendly dashboard.</p>

    <h2>🚀 Components</h2>
    <ul>
        <li><strong>Prometheus</strong> 🟢: Collects and stores metrics.</li>
        <li><strong>Grafana</strong> 📊: Visualizes metrics with interactive dashboards.</li>
        <li><strong>Alertmanager</strong> ⚠️: Handles and manages system alerts.</li>
        <li><strong>Node Exporter</strong> 💻: Exports host hardware and OS metrics to Prometheus.</li>
    </ul>

    <h2>📂 Project Structure</h2>
    <pre>
monitoring-project/
├── ansible.cfg
├── inventory/
│   └── hosts       # Define connection to localhost
├── playbooks/
│   ├── monitoring-stack.yml   # Deploys Prometheus, Grafana, Alertmanager
│   └── node-exporter.yml      # Deploys Node Exporter
└── roles/                     # Contains individual tasks and config files
    </pre>

    <h2>⚙️ Prerequisites</h2>
    <ul>
        <li>A Linux VM (Ubuntu/Debian recommended) 🐧</li>
        <li>Python 3 and Ansible installed 🐍</li>
        <li>Podman installed 🐳</li>
        <li>Sudo privileges to manage containers 🔑</li>
    </ul>

    <h2>🛠️ Deployment Steps</h2>
    <ol>
        <li><strong>Create the monitoring network</strong>:<br>
            <code>sudo podman network create monitoring_net</code>
        </li>
        <li><strong>Deploy the Centralized Stack</strong>:<br>
            <code>ansible-playbook playbooks/monitoring-stack.yml --ask-become-pass</code>
        </li>
        <li><strong>Deploy Node Exporter</strong>:<br>
            <code>ansible-playbook playbooks/node-exporter.yml --ask-become-pass</code>
        </li>
    </ol>

    <h2>🌐 Accessing the Services</h2>
    <ul>
        <li><strong>Prometheus</strong>: <a href="http://localhost:9090">http://localhost:9090</a></li>
        <li><strong>Alertmanager</strong>: <a href="http://localhost:9093">http://localhost:9093</a></li>
        <li><strong>Grafana</strong>: <a href="http://localhost:3000">http://localhost:3000</a><br>
            Default login: <code>admin</code> / <code>admin</code>
        </li>
    </ul>

    <h2>🎯 Features</h2>
    <ul>
        <li>Centralized monitoring for local hosts</li>
        <li>Real-time system metrics visualization</li>
        <li>Alert management for critical events</li>
        <li>Fully automated deployment using Ansible & Podman</li>
    </ul>
</body>
</html>
