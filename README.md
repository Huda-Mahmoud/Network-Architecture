# Network-Architecture
A School with 2 connected buildings, each is 2 floors (9 grades, each grade has 6 classes) 

#  School Network Design using Cisco Packet Tracer

This project presents a network design for a school composed of **2 buildings**, each having **2 floors**. The network connects students, teachers, and administrative staff using VLANs and provides secure access to the internet.

---

## Network Overview

- **2 buildings × 2 floors**
- **9 grades × 6 classes per grade = 54 classrooms**
- **Each classroom has 20 students (Total ≈ 1080 users)**
- **80 employees (teachers + administrative staff)**

---

## Components Used

| Device              | Model                   | Quantity |
|---------------------|-------------------------|----------|
| Router              | Cisco 2811              | 1        |
| Core Switch         | Cisco 2960              | 1        |
| Access Switches     | Cisco 2960              | 4        |
| PCs                 | Generic PC              | 12       |
| Server              | Generic Server          | 1        |
| Cloud (Internet)    | Cloud (simulated)       | 1        |
| Wireless Access Points (optional) | Cisco WAP or TP-Link | 8    |

---

## VLAN Structure

| VLAN Name | VLAN ID | Used For      |
|-----------|---------|---------------|
| Students  | 10      | Classroom PCs |
| Teachers  | 20      | Teacher PCs   |
| Admins    | 30      | Admin PCs     |

---

## Configuration Summary

### Switch VLAN Configuration:
```bash
vlan 10
 name Students
vlan 20
 name Teachers
vlan 30
 name Admins

interface fa0/1
 switchport mode access
 switchport access vlan 10

