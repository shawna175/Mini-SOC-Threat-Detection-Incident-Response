# Mini Security Operations Center (SOC)

**Real-Time Threat Detection and Incident Response in an Isolated Virtual Environment**

A hands-on cybersecurity project demonstrating centralized security monitoring, threat detection, event investigation, and incident response using Wazuh, Suricata, Sysmon, and UFW in an isolated VirtualBox laboratory.

This project was completed as part of **CSE 487 – Cyber Security, Law, and Ethics** at **East West University**.

## Objectives

- Deploy a centralized Wazuh platform for security monitoring and event analysis.
- Enroll a Windows endpoint and collect security telemetry using the Wazuh Agent and Microsoft Sysmon.
- Demonstrate File Integrity Monitoring (FIM).
- Integrate Suricata network intrusion-detection events with Wazuh.
- Generate controlled network reconnaissance and authentication-failure events.
- Investigate security alerts and relevant MITRE ATT&CK mappings.
- Apply and validate a firewall-based incident-response action.

## Technologies Used

| Technology | Purpose |
|---|---|
| Wazuh 4.14.7 | Centralized security monitoring and event analysis |
| Suricata 8.0.6 | Network intrusion detection |
| Microsoft Sysmon | Windows endpoint telemetry |
| Ubuntu 24.04.4 LTS | SOC server |
| Windows 11 Pro | Monitored endpoint |
| Kali Linux 2026.2 | Controlled security testing |
| UFW | Firewall-based response |
| Oracle VirtualBox | Isolated virtual laboratory |
| Nmap | Network reconnaissance testing |

## Lab Architecture

The laboratory consists of three systems connected through a VirtualBox Host-Only network.

- **Ubuntu SOC Server:** Hosts Wazuh Manager, Indexer, Dashboard, Suricata, and UFW.
- **Windows Endpoint:** Sends endpoint security events through the Wazuh Agent and Sysmon.
- **Kali Linux Test Host:** Generates controlled reconnaissance and authentication-testing activity.

### Network Configuration

| Component | Operating System | Host-Only IP |
|---|---|---|
| SOC Server | Ubuntu 24.04.4 LTS | `192.168.56.101` |
| Windows Endpoint | Windows 11 Pro | `192.168.56.1` |
| Test Host | Kali Linux 2026.2 | `192.168.56.102` |

## Key Implementations

### 1. Centralized Monitoring with Wazuh
Deployed the Wazuh all-in-one platform and verified the manager, indexer, dashboard, and required communication ports.

### 2. Windows Endpoint Monitoring
Enrolled a Windows endpoint using the Wazuh Agent and integrated Sysmon to collect detailed system activity.

### 3. File Integrity Monitoring
Configured Wazuh FIM to monitor a dedicated test directory and detect controlled file modifications.

### 4. Network Intrusion Detection
Installed Suricata in IDS mode and integrated its EVE JSON event stream with Wazuh.

### 5. Controlled Security Testing
Performed authorized network reconnaissance and SSH authentication-failure tests from the Kali Linux test host.

### 6. Incident Response and Validation
Applied a UFW rule to block the test host from accessing SSH. Repeated the connection test to validate the mitigation through a connection timeout.

## Results

The laboratory demonstrated the following capabilities:

- Successful Wazuh deployment and Windows endpoint enrollment.
- Collection and visualization of Sysmon events.
- Detection of a controlled file modification through FIM.
- Suricata-based network activity monitoring and explicit scan detection.
- Detection of two SSH authentication failures.
- Generation and local verification of Windows Event ID `4625`.
- Validation of a UFW-based SSH blocking action.

These results demonstrate a practical workflow covering monitoring, detection, investigation, mitigation, and verification in an isolated environment.

## Repository Structure

```text
Mini-SOC-Threat-Detection-Incident-Response/
├── README.md
├── docs/
│   └── Project_Report.pdf
├── screenshots/
│   └── (Selected project evidence)
└── └── demo/
    └── Demo video is available in the Demo Video section
```

Add the `screenshots/` and `demo/` materials if you choose to include them. Avoid uploading credentials, private keys, or sensitive system information.

## Documentation and Demonstration

- - **Project Report:** [View Project Report](docs/Project_Report_SOC.pdf)
- - **Demo Video:** [Watch Mini-SOC Demo](https://drive.google.com/file/d/1Ghq65fDM1LUWb7D3sKzIdW2S_LH5_zzU/view?usp=sharing)

The report documents the lab architecture, implementation steps, command summaries, test evidence, results, challenges, and security recommendations.

## Safety and Ethical Considerations

All scanning, authentication testing, monitoring, and firewall validation were performed within an authorized, isolated VirtualBox laboratory.

This project is intended for educational and defensive cybersecurity purposes. Do not use the testing procedures against public, institutional, or third-party systems without explicit authorization.

## Academic Context

**Course:** CSE 487 – Cyber Security, Law, and Ethics  
**Institution:** East West University  
**Author:** Shawna Akter
