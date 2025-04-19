# 🛡️ Network-IDS-Dashboard

**Network-IDS-Dashboard** is a lightweight, open-source network monitoring stack based on Docker. It integrates **Suricata** (IDS), **Filebeat**, **Elasticsearch**, and **Kibana** into a plug-and-play setup that helps you detect and visualize suspicious network activity in real time.

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

---

## 📊 Access the Dashboard

- Kibana UI: http://localhost:5601
- Elasticsearch: http://localhost:9200

Once Kibana is up:

1. Go to Stack Management → Index Patterns
2. Create a new pattern: `suricata-*`
3. Use `@timestamp` as the time field
4. Start exploring dashboards and alerts!

---

## 🧪 Testing the Setup

To generate some traffic:

```bash
ping 8.8.8.8
curl http://example.com
nmap localhost
```

Suricata will log alerts into `eve.json`, which Filebeat sends to Elasticsearch for Kibana to visualize.

---

## ⚙️ Configuration Tips

- **Network Monitoring Interface**: Suricata uses `eth0` by default. Modify the interface in `docker-compose.yml` or Suricata config if needed.
- **Custom Rules**: Place custom Suricata rules in `suricata/etc/` and mount it into the container.
- **Filebeat**: Customize the `filebeat.yml` to fit your logging and output preferences.

---

## 🐳 Requirements

- Docker
- Docker Compose
- Linux host recommended (for `network_mode: host`)

### Basic Commands

```bash
# Start the stack
docker-compose up -d

# Stop and clean up
docker-compose down -v
```

---

## 📚 Resources

- [Suricata Documentation](https://suricata.readthedocs.io/)
- [Filebeat Documentation](https://www.elastic.co/guide/en/beats/filebeat/current/index.html)
- [Kibana Documentation](https://www.elastic.co/guide/en/kibana/current/index.html)

---

## 📖 License

MIT License