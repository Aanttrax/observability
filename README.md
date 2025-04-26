
# 📈 Docker Observability Stack

This repository sets up a full **observability** environment for Docker Compose services, using:

- **Prometheus**: Metric collection.
- **Grafana**: Visualization of metrics and logs.
- **cAdvisor**: Monitoring of Docker containers.
- **Node Exporter**: Monitoring of the host system.
- **Loki**: Log storage.
- **Promtail**: Log collection from containers.
- **Nginx**: Service to expose to a master nginx.

---

## 🚀 Technologies Used

| Component  | Description |
|:-----------|:------------|
| **Prometheus** | Scrapes metrics from containers and the host system. |
| **Grafana** | Dashboard for visualizing metrics and logs. |
| **cAdvisor** | Metrics for each container (CPU, RAM, Disk, Network). |
| **Node Exporter** | Metrics for the host OS (CPU, RAM, Disk, Network). |
| **Loki** | Log database. |
| **Promtail** | Log collector for Loki. |
| **Nginx** | Service to expose to a master nginx. |

---

## 🛠️ How to Run the Stack

1. Clone the repository:

```bash
git clone https://github.com/Aanttrax/observability.git
cd observability
```

2. Create the `.env` file for Grafana credentials:

```bash
echo "GF_SECURITY_ADMIN_USER=admin" >> .env
echo "GF_SECURITY_ADMIN_PASSWORD=admin" >> .env
```

(Modify values for enhanced security)

3. Launch the services:

```bash
docker-compose up -d
```

4. Access Grafana:

- URL: [http://localhost:3000](http://localhost:3000)
- Username: `admin`
- Password: `admin` (or whatever you set in `.env`)

---

## 📄 Repository Structure

```plaintext
├── docker-compose.yml
├── prometheus.yml
├── grafana.ini
├── loki-config.yml
├── promtail-config.yml
├── observability.conf
└── README.md
```

---

## 🔥 Exposed Services

| Service          | Access URL                  |
|:-----------------|:----------------------------|
| **Grafana**      | [http://localhost:3000](http://localhost:3000) |

---

## 📊 Recommended Dashboards

- Node Exporter Full (by Prometheus)
- Docker Containers Metrics (by cAdvisor)
- Loki Logs Explorer (by Loki)
- Prometheus Metrics Overview

*(You can import these dashboards directly in Grafana using their ID from Grafana.com or by uploading the JSON files.)*

---

## 🧠 Important Notes

- **cAdvisor** automatically detects all running containers.
- **Promtail** collects logs from `/var/log/containers/` automatically.
- This stack is **not production-ready** (e.g., Grafana without HTTPS). Use it only in controlled environments.

---

## 🧹 To Clean Up

```bash
docker-compose down -v
```
*(This removes containers, networks, and volumes.)*

---

# ✨ Author
> Stack created by Aanttrax — inspired by modern observability practices.

