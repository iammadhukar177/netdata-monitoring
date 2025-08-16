# 📊 Monitor System Resources Using Netdata

## 🎯 Objective
Install Netdata using Docker and monitor system and application performance metrics through its web dashboard.

---

## 🛠 Tools Used
- Netdata (lightweight monitoring tool)
- Docker

---

## ✅ Deliverables
- 📸 Screenshot of Netdata dashboard
- 📈 Screenshot showing system metrics

---

## 🚀 Step-by-Step Guide

### 1️⃣ Install Docker (if not already installed)
For Ubuntu users:

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
```

---

### 2️⃣ Run Netdata via Docker

```bash
docker run -d --name=netdata \
  -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```

This command does the following:
- Downloads and starts Netdata in a container
- Maps Netdata’s port 19999 to your host
- Enables system-level monitoring

---

### 3️⃣ Access the Dashboard

Open your browser and visit:  
👉 `http://localhost:19999`  

You’ll see the real-time system monitoring dashboard.

![Netdata Dashboard](dashboard.png)

---

### 4️⃣ Monitor System Metrics

Once inside the dashboard, you can monitor:
- **CPU usage**
- **Memory consumption**
- **Disk I/O**
- **Network traffic**
- **Docker container performance**

Example metrics screenshot:

![System Metrics](metrics.png)

---

### 5️⃣ View Logs

To explore logs inside the container:

```bash
docker exec -it netdata bash
cd /var/log/netdata
ls
cat error.log
```

---

### 🧹 Stop and Remove Netdata

```bash
docker stop netdata
docker rm netdata
```

---

## 🧠 Outcome
You’ve successfully learned how to:
- Deploy Netdata with Docker
- Visualize system performance in real time
- Access system alerts, charts, and logs

---

## 📁 Suggested Project Structure

```
netdata-monitoring/
├── README.md
├── dashboard.png
└── metrics.png
```
