# 🚀 High Availability & Load Balancing Setup (Keepalived + HAProxy)

> 💡 Designed and implemented a production-like High Availability architecture ensuring minimal downtime and continuous service availability.

---

## 📌 Overview

This project demonstrates a **High Availability (HA)** and **Load Balancing** solution using:

* **Keepalived (VRRP)** → Provides automatic failover using Virtual IP (VIP)
* **HAProxy** → Distributes incoming traffic across backend servers

This setup ensures:

* Zero downtime
* Automatic failover
* Efficient traffic distribution

---

## 🧠 Architecture

Client → VIP (Port 5000) → HAProxy → Backend Servers (Port 80)

* **MASTER Node:** 192.168.142.144
* **BACKUP Node:** 192.168.142.146

### 🔹 Virtual IPs (VIP)

* 192.168.142.200
* 192.168.142.201
* 192.168.142.202

---

## ⚙️ Technologies Used

* RHEL 8.9
* Keepalived (VRRP Protocol)
* HAProxy
* VMware Workstation

---

## 🔧 Configuration Details

### 🔹 Keepalived (High Availability)

* Configured MASTER and BACKUP nodes
* Implemented VRRP for failover
* Assigned multiple Virtual IPs

### 🔹 HAProxy (Load Balancer)

* Configured frontend on port **5000**
* Backend servers running on port **80**
* Implemented **round-robin load balancing**

---

## ⚙️ Setup Steps

1. Installed Keepalived on both nodes
2. Configured MASTER and BACKUP roles
3. Assigned Virtual IPs (VIP)
4. Installed and configured HAProxy
5. Enabled and started services
6. Verified connectivity and failover

---

## 🔁 Failover Logic

* MASTER node holds the VIP during normal operation
* If MASTER fails → BACKUP node automatically takes over VIP
* HAProxy continues serving traffic without interruption

---

## 🧪 Testing & Validation

* Stopped Keepalived on MASTER → VIP successfully moved to BACKUP ✅
* Stopped HAProxy on MASTER → Failover triggered correctly ✅
* Accessed application via VIP from client machine ✅
* Verified load balancing across backend servers ✅

---

## 📁 Project Structure

```
keepalived-ha-setup/
│
├── keepalived-master.conf
├── keepalived-backup.conf
├── haproxy.cfg
└── README.md
```

---

## ✅ Result

* Achieved High Availability with automatic failover
* Ensured zero downtime during node failure
* Successfully implemented load balancing
* Built a production-style resilient architecture

---

## 🎯 Key Learnings

* VRRP protocol and Keepalived configuration
* High Availability architecture design
* Load balancing using HAProxy
* Failover testing and troubleshooting

---

## 👨‍💻 Author

**Sachin Chaudhary**
System Engineer | Linux | DevOps Enthusiast
