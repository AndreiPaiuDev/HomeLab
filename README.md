🏢 Active Directory Enterprise Homelab
This project recreates a complete enterprise‑style Active Directory environment inside a homelab, including OU design, GPO separation, workstation policies, and security hardening aligned with real corporate practices.

📁 Active Directory Structure
```
homelab.local
 ├── Departments
 │    ├── HR
 │    ├── IT
 │    └── Sales
 ├── Workstations
 └── Domain Controllers
```

![Active Directory Structure](IMG01.png)

### Visual Diagram
```mermaid
graph TD
	A[homelab.local Domain]
	A --> B[Organizational Units]
	B --> C[Departments]
	B --> D[Workstations]
	B --> E[Domain Controllers]
	B --> F[Group Policy Objects]
	C --> G[HR]
	C --> H[IT-Workstations]
	C --> I[Sales]
	G --> J[HR-Restrictions (User GPO)]
	J --> J1[CMD disabled]
	J --> J2[PowerShell disabled]
	J --> J3[Control Panel blocked]
	J --> J4[Settings hidden]
	H --> K[IT-Workstation-Policy (Comp GPO)]
	K --> K1[PowerShell enabled]
	K --> K2[Script Block Logging]
	K --> K3[Module Logging]
	K --> K4[Remote Desktop enabled]
	K --> K5[CMD allowed]
	K --> K6[IT-Helpdesk → Local Admins]
	K --> K7[RSAT visibility enabled]
	I --> L[Sales-Restrictions (User GPO)]
	L --> L1[CMD disabled]
	L --> L2[PowerShell disabled]
	L --> L3[Control Panel blocked]
```

👥 Department Policies
🔹 **HR‑Restrictions (User GPO)**
	- CMD disabled
	- PowerShell disabled
	- Control Panel & Settings blocked
	- Settings app hidden
	- Department wallpaper applied
	- Fully restricted environment for non‑technical staff

![HR-Restrictions 1](IMG02.png)
![HR-Restrictions 2](IMG03.png)
![HR-Restrictions 3](IMG04.pnn)

🔹 **IT‑Workstation‑Policy (Computer GPO)**
	- PowerShell enabled (Allow all scripts)
	- Script Block Logging enabled
	- Module Logging enabled
	- Remote Desktop enabled
	- CMD allowed
	- IT‑Helpdesk added to Local Administrators

![IT‑Workstation‑Policy](Graphics.webp)


🔹 **Sales‑Restrictions (User GPO)**
	- CMD disabled
	- PowerShell disabled
	- Control Panel blocked

![Sales‑Restrictions 1](IMG02.png)
![Sales‑Restrictions 2](IMG03.png)
![Sales‑Restrictions 3](IMG04.pnn)

🧩 Key Features Implemented
- Role‑based access control via IT‑Helpdesk
- Advanced PowerShell auditing
- Drive Maps using Group Policy Preferences
- Department‑specific security baselines
- Clean, scalable OU structure
- Centralized ADMX management

🛠️ Technologies Used
- Windows Server 2022
- Active Directory Domain Services
- Group Policy Management
- Windows 10 Enterprise
- PowerShell
- SYSVOL Central Store (ADMX)

---

## 🚧 Next Steps (Planned Updates)

This homelab is actively evolving. The following enhancements are planned for upcoming updates:

### 🔐 Workstation Hardening
- Implement AppLocker rules (allow‑list model)
- Disable USB mass‑storage devices
- Restrict Task Manager and Run dialog for non‑IT departments
- Enforce Windows Firewall rules per department

### 🧩 Group Policy Expansion
- Create a dedicated **Sales‑Workstation‑Policy** for computer‑level restrictions
- Add login banners and compliance notices
- Configure advanced audit policies (logon events, object access, privilege use)

### 🛡️ Security & Monitoring
- Deploy Wazuh agents across all workstations
- Forward Windows Event Logs to SIEM
- Configure alerting rules for PowerShell, RDP, and authentication anomalies

### 🌐 Network Segmentation
- Introduce VLANs for HR, IT, Sales, and Servers
- Configure DHCP scopes per VLAN
- Implement DNS scavenging and conditional forwarding

### 🗂️ Infrastructure Enhancements
- Add a second Domain Controller for redundancy
- Implement DFS‑R for SYSVOL replication
- Introduce a file server with departmental NTFS permissions

### 🧪 Automation & Scripting
- Automate user creation with PowerShell
- Automate OU provisioning and GPO linking
- Script workstation onboarding (domain join + baseline config)

### 📊 Documentation & Visualization
- Add a full architecture diagram (network + AD + GPO layers)
- Add screenshots for each GPO configuration
- Add a PDF version of the project for portfolio use

---