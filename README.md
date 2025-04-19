# 🛡️ NetSentinel

**NetSentinel** is a lightweight, open-source network monitoring stack based on Docker. It integrates **Suricata** (IDS), **Filebeat**, **Elasticsearch**, and **Kibana** into a plug-and-play setup that helps you detect and visualize suspicious network activity in real time.

---

## 📦 Stack Overview

| Component     | Role                                           |
| ------------- | ---------------------------------------------- |
| Suricata      | Network Intrusion Detection System (IDS)       |
| Filebeat      | Log shipper that forwards Suricata logs        |
| Elasticsearch | Stores and indexes log data                    |
| Kibana        | Visualizes network alerts and patterns         |

---

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/netsentinel.git
cd netsentinel

📊 Access the Dashboard
Kibana UI: http://localhost:5601

Elasticsearch: http://localhost:9200

Once Kibana is up:

Go to Stack Management → Index Patterns

Create a new pattern: suricata-*

Use @timestamp as the time field

Start exploring dashboards and alerts!

🧪 Testing the Setup
To generate some traffic:

bash
Copiar
Editar
ping 8.8.8.8
curl http://example.com
nmap localhost
Suricata will log alerts into eve.json, which Filebeat sends to Elasticsearch for Kibana to visualize.

⚙️ Configuration Tips
Network Monitoring Interface: Suricata uses eth0 by default. Modify the interface in docker-compose.yml or Suricata config if needed.

Custom Rules: Place custom Suricata rules in suricata/etc/ and mount it into the container.

Filebeat: Customize the filebeat.yml to fit your logging and output preferences.

🐳 Requirements
Docker

Docker Compose

docker-compose up -d


Linux host recommended (for network_mode: host)

📚 Resources
Suricata Docs

Filebeat Docs

Kibana Docs

📖 License
MIT License