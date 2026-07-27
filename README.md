# Secure Corporate Network Architecture

## 📌 Project Overview
This project simulates a complete and secure corporate network infrastructure designed for a multi-departmental organization. Built using Cisco Packet Tracer, the architecture focuses on logical segmentation, automated IP allocation, and strict access control policies to ensure data confidentiality and network integrity. 

## 🛡️ Security & Access Control (ACLs)
A core component of this architecture is the implementation of robust security policies using Access Control Lists (ACLs) to mitigate internal threats and control inter-VLAN traffic:
*   **Guest Network Isolation:** The Guest network is strictly prohibited from accessing internal corporate data in the IT and HR departments.
*   **Controlled Server Access:** Guests are granted limited access to the internal server strictly via HTTP; ICMP (ping) requests are actively blocked to prevent network mapping.
*   **Inter-Departmental Restrictions:** The HR department is isolated from the IT department's network to maintain separation of privileges.
*   **Administrative Access:** The IT department is granted full, unrestricted access across all VLANs and internal servers for management purposes.
*   **Secure External Routing:** The internal private networks are hidden behind NAT overload (PAT) when accessing the external internet, providing an additional layer of security.

## 🏗️ Network Topology & Segmentation
The corporate network is logically segmented into dedicated VLANs to optimize traffic flow and enforce security boundaries:
*   **VLAN 10 (IT):** Dedicated network for the IT Department.
*   **VLAN 20 (HR):** Dedicated network for the Human Resources Department.
*   **VLAN 30 (GUEST):** Isolated network for company visitors.
*   **VLAN 40 (SERVERS):** Secure zone hosting internal services.

*Note: Please refer to the topology screenshot included in this repository for a visual representation of the routers, switches, and endpoint connections.*

## ⚙️ Core Infrastructure Features
Beyond security, the network demonstrates enterprise-level infrastructure configurations:
*   **Inter-VLAN Routing:** Implemented via a "Router-on-a-Stick" configuration with dedicated subinterfaces for each department.
*   **Dynamic Routing:** OSPF is configured between the corporate edge router (CE) and the ISP router to ensure reliable external connectivity.
*   **Automated Provisioning:** An internal DHCP server dynamically assigns IP addresses, default gateways, and DNS information to clients in VLANs 10, 20, and 30, utilizing DHCP Relay (IP Helper) on the router.
*   **Internal Services:** A dedicated internal server provides DNS resolution (`www.firma.local`) and hosts an internal HTTP Web Server.

## 🚀 How to Explore this Project
1. Clone this repository to your local machine.
2. Open the `.pkt` file using Cisco Packet Tracer.
3. Review the router and switch configurations to inspect the ACLs, OSPF routing tables, and VLAN setups.
