# 🏭 Industrial Network Segmentation & WSUS Documentation

> Simulated OT/IT network segmentation and patch management architecture for an industrial SCADA environment.

---

## 📋 Project Overview

This project documents the design and architecture of a secure network segmentation model for an industrial environment, including a WSUS (Windows Server Update Services) update flow for isolated Operational Technology (OT) networks.

All IP addresses and network details used in this project are **simulated and fictional** for educational purposes.

---

## 🗂️ Contents

| File | Description |
|------|-------------|
| `wsus_design_flow.pdf` | WSUS Design & Flow diagram |
| `README.md` | Project documentation |

---

## 🔧 Key Concepts Covered

- **OT/IT Network Segmentation** — Separating Process Automation Networks (PAN) from standard IT infrastructure
- **DMZ Architecture** — Using a Demilitarized Zone as a security buffer between the internet and internal systems
- **WSUS Patch Management** — Controlled update distribution to isolated OT endpoints without direct internet access
- **Firewall Policy** — Outbound HTTPS-only firewall rules to minimize attack surface
- **GPO-based Update Control** — Using Group Policy to enforce update source for PAN clients

---

## 🖼️ WSUS Design & Flow

![WSUS Design](wsus-diagram.png)

### How It Works:

```
Microsoft Update → Internet → Firewall (HTTPS Only) → DMZ-WSUS Server → DMZ Network → PAN Clients
```

**Approval Workflow:**
1. Admin logs into DMZ-WSUS and reviews available updates
2. Only "approved" updates are made available to PAN clients via GPO
3. PAN clients **never** connect to the internet directly — all updates come from DMZ-WSUS

---

## 🛡️ Security Design Principles

| Principle | Implementation |
|-----------|----------------|
| Network Isolation | PAN completely isolated from internet |
| Least Privilege | Firewall allows outbound HTTPS only |
| Controlled Updates | All patches reviewed before deployment |
| DMZ Buffer | Separate zone between internet and internal network |
| Air-gap Simulation | OT devices receive updates only from internal WSUS |

---

## 🧰 Tools & Technologies

- Microsoft WSUS
- Firewall (Outbound HTTPS policy)
- DMZ Network Architecture
- Group Policy Objects (GPO)
- ICS/SCADA Security Concepts
- Network Diagramming


---

## 👩‍💻 Author

**Elaf Alharbi**  
IT Graduate | Cybersecurity Enthusiast  
[LinkedIn](https://linkedin.com/in/elaf-alharbi) 

---

> *This project was developed as part of industrial cybersecurity training focusing on OT/IT security architecture.*
