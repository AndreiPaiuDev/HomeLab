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

<img scr="./Images/IMG01.png"></img>

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

<h1 align="center">🏢 Active Directory Enterprise Homelab</h1>


<b>🔑 Project Overview</b><br>
This project recreates a complete enterprise‑style Active Directory environment inside a homelab, including OU design, GPO separation, workstation policies, and security hardening aligned with real corporate practices.

<b>📁 Active Directory Structure</b>
<pre>
homelab.local
 ├── Departments
 │    ├── HR
 │    ├── IT
 │    └── Sales
 ├── Workstations
 └── Domain Controllers
</pre>

<b>👥 Department Policies</b>


<b>HR‑Restrictions (User GPO)</b>
<ul>
    <li>CMD disabled</li>
    <li>PowerShell disabled</li>
    <li>Control Panel & Settings blocked</li>
    <li>Settings app hidden</li>
    <li>Department wallpaper applied</li>
    <li>Fully restricted environment for non‑technical staff</li>
</ul>

<p align="center">
		<img src="./Images/IMG01.png" width="25%" />
		<img src="./Images/IMG02.png" width="25%" />
		<img src="./Images/IMG03.png" width="25%" />
		<img src="./Images/IMG04.png" width="25%" />
</p>

<b>IT‑Workstation‑Policy (Computer GPO)</b>
<ul>
    <li>PowerShell enabled (Allow all scripts)</li>
    <li>Script Block Logging enabled</li>
    <li>Module Logging enabled</li>
    <li>Remote Desktop enabled</li>
    <li>CMD allowed</li>
    <li>IT‑Helpdesk added to Local Administrators</li>
    <li>RSAT visibility enabled</li>
</ul>

<p align="center">
		<img src="./Images/Graphics.webp" width="50%" />
</p>

<b>Sales‑Restrictions (User GPO)</b>
<ul>
    <li>CMD disabled</li>
    <li>PowerShell disabled</li>
    <li>Control Panel blocked</li>
    <li>Wallpaper applied</li>
    <li>Drive mapping via GPP: S: → \\dc01\shares\sales</li>
</ul>
<p align="center">
		<img src="./Images/IMG01.png" width="25%" />
		<img src="./Images/IMG02.png" width="25%" />
		<img src="./Images/IMG03.png" width="25%" />
		<img src="./Images/IMG04.png" width="25%" />
</p>

<b>🧩 Key Features Implemented</b>
<ul>
    <li>Role‑based access control via IT‑Helpdesk</li>
    <li>Advanced PowerShell auditing</li>
    <li>Drive Maps using Group Policy Preferences</li>
    <li>Department‑specific security baselines</li>
    <li>Clean, scalable OU structure</li>
    <li>Centralized ADMX management</li>
</ul>

<b>🛠️ Tech Stack</b>
<table>
	<tr>
		<th><b>Category</b></th>
		<th><b>Technologies</b></th>
	</tr>
	<tr>
		<td><b>Server OS</b></td>
		<td>Windows Server 2022</td>
	</tr>
	<tr>
		<td><b>Directory Services</b></td>
		<td>Active Directory Domain Services</td>
	</tr>
	<tr>
		<td><b>Policy Management</b></td>
		<td>Group Policy Management, Centralized ADMX</td>
	</tr>
	<tr>
		<td><b>Workstations</b></td>
		<td>Windows 10 Enterprise</td>
	</tr>
	<tr>
		<td><b>Scripting</b></td>
		<td>PowerShell</td>
	</tr>
</table>

<b>📁 Project Structure</b>
<pre>
Code
homelab.local/
 ├── Departments/
 │    ├── HR/
 │    ├── IT/
 │    └── Sales/
 ├── Workstations/
 ├── Domain Controllers/
 ├── Group Policy Objects/
 └── Security Baselines/
</pre>


<b>🚧 Next Steps (Planned Updates)</b>
<ul>
		<li>🔐 Workstation Hardening: AppLocker, USB restrictions, Task Manager/Run dialog lockdown, Windows Firewall rules</li>
		<li>🧩 Group Policy Expansion: Sales workstation policy, login banners, advanced audit policies</li>
		<li>🛡️ Security & Monitoring: Wazuh agents, SIEM log forwarding, alerting for PowerShell/RDP/auth anomalies</li>
		<li>🌐 Network Segmentation: VLANs, DHCP scopes, DNS scavenging/forwarding</li>
		<li>🗂️ Infrastructure Enhancements: Second DC, DFS-R, file server with NTFS permissions</li>
		<li>🧪 Automation & Scripting: PowerShell user/OU/GPO automation, workstation onboarding</li>
		<li>📊 Documentation & Visualization: Architecture diagram, GPO screenshots, PDF portfolio</li>
</ul>