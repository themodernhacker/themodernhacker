<!-- ====================== HEADER ====================== -->
<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,2,5,30&height=230&section=header&text=The%20Modern%20Hacker&fontSize=55&fontColor=ffffff&animation=twinkling&fontAlignY=36&desc=Abhishek%20K.%20Sahu%20%E2%80%A2%20Cybersecurity%20Analyst%20%7C%20SOC%20%C2%B7%20Detection%20Engineering%20%C2%B7%20Purple%20Team&descAlignY=56&descAlign=50" />

<a href="https://github.com/themodernhacker">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=00F260&center=true&vCenter=true&width=820&lines=Cybersecurity+Analyst+%7C+SOC+%26+Detection+Engineering+%F0%9F%9B%A1;MSc+Cybersecurity+%26+AI+%7C+University+of+Sheffield;Microsoft+Sentinel+%7C+KQL+%7C+MITRE+ATT%26CK;Purple+Team+%3A+Offensive+Recon+to+Defensive+Detection;CompTIA+Security%2B+%7C+SC-900+%7C+AZ-900+%7C+eJPT;I+build+honeypots%2C+break+them%2C+then+detect+the+break" alt="Typing SVG" />
</a>

<br/>

[![Website](https://img.shields.io/badge/Portfolio-themodernhacker.com-00F260?style=for-the-badge&logo=firefox&logoColor=black)](https://themodernhacker.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/themodernhacker)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:abhisahu518@gmail.com)
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://twitter.com/themodernhacker)
[![Medium](https://img.shields.io/badge/Medium-000000?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@themodernhacker)

<img src="https://komarev.com/ghpvc/?username=themodernhacker&label=Profile+Views&color=00F260&style=flat-square" alt="Profile views" />
<img src="https://img.shields.io/badge/Right%20to%20Work-UK%20Graduate%20Visa-00F260?style=flat-square" alt="Right to work" />
<img src="https://img.shields.io/badge/Status-DBS%20Cleared-00F260?style=flat-square" alt="DBS" />

</div>

---

## `whoami`

```bash
┌──(abhi㉿themodernhacker)-[~]
└─$ whoami --full

  NAME         : Abhishek Kumar Sahu   (aka "The Modern Hacker")
  ROLE         : Cybersecurity Analyst  |  SOC · Detection Engineering · Purple Team
  EDUCATION    : MSc Cybersecurity & Artificial Intelligence — University of Sheffield (NCSC-certified)
  LOCATION     : United Kingdom  🇬🇧   (Graduate Visa · Full Right to Work · DBS Cleared)
  FOCUS        : Threat Detection · SIEM · Security Automation · Offensive ⇄ Defensive
  CORE STACK   : Microsoft Sentinel · KQL · Wazuh · MITRE ATT&CK · Kali Linux · Docker
  IN PROGRESS  : eJPT  →  next: SC-200 (Security Operations Analyst)
  MINDSET      : "Detections that map to real attacker behaviour. Automation correct by design."
```

---

## ⚔️ Featured Projects

<div align="center">

### 🍯 Honeypot → SIEM · Purple-Team Detection Lab

[![Repo](https://img.shields.io/badge/GitHub-honeypot--siem-00F260?style=for-the-badge&logo=github&logoColor=black)](https://github.com/themodernhacker/honeypot-siem)
[![Wazuh](https://img.shields.io/badge/SIEM-Wazuh%204.9-2962FF?style=for-the-badge)](https://github.com/themodernhacker/honeypot-siem)
[![MITRE](https://img.shields.io/badge/Mapped%20to-MITRE%20ATT%26CK-E02041?style=for-the-badge)](https://github.com/themodernhacker/honeypot-siem)

</div>

> A self-contained purple-team lab that captures **real attacker activity end-to-end** — an SSH honeypot (Cowrie) ships its events into a Wazuh SIEM, custom rules catch the attacks, and every alert is mapped to MITRE ATT&CK. Built entirely in Docker on one machine: **attack it → detect it → document it.**

**🎯 What it demonstrates**
- ✍️ **11 custom Wazuh detection rules** with frequency-based correlation, in version control
- 🗺️ Every alert tagged to a **MITRE ATT&CK technique** — recon → brute force → compromise → discovery → tool transfer
- 🔁 The same core detections rewritten as **5 KQL queries for Microsoft Sentinel** (cross-SIEM portability)
- 🐍 Scripted, controlled attacks (Python / `paramiko` brute force, recon, scanning) drive the lab
- 📝 Per-attack write-ups tracing **log → rule → ATT&CK technique → analyst next step**

| Detection | MITRE ATT&CK | Severity |
|-----------|:------------:|:--------:|
| SSH brute force (8+ fails / 120s, one source) | `T1110` | 🔴 High |
| Successful login **after** brute force (compromise) | `T1078` + `T1110` | 🔴 Critical |
| Post-access recon (`uname`, `id`, `whoami`) | `T1082` / `T1033` | 🟠 Medium |
| Second-stage payload pull (`wget` / `curl`) | `T1105` | 🔴 High |
| Tunnel / proxy attempt via honeypot | `T1090` | 🟠 Medium |
| Rapid automated connections | `T1046` | 🟡 Low |

> 💡 *Real engineering, honestly scoped:* debugged a silent correlation failure (Wazuh keying on `srcip` vs Cowrie's dynamic `src_ip`), and documented the honeypot's genuine blind spots rather than overstating coverage.

`Cowrie` `Wazuh 4.9` `Docker Compose` `Python (paramiko)` `MITRE ATT&CK` `Microsoft Sentinel` `KQL`

---

<div align="center">

### 🛡️ Ansible-Inspired RBAC Security Automation in Standard ML

[![Repo](https://img.shields.io/badge/GitHub-RBAC--Automation--SML-00F260?style=for-the-badge&logo=github&logoColor=black)](https://github.com/themodernhacker/Ansible-like-RBAC-Automation-in-Standard-ML)
[![Type](https://img.shields.io/badge/MSc-Dissertation-7D2196?style=for-the-badge)](https://github.com/themodernhacker/Ansible-like-RBAC-Automation-in-Standard-ML)
[![Lang](https://img.shields.io/badge/Standard-ML-DD0031?style=for-the-badge)](https://github.com/themodernhacker/Ansible-like-RBAC-Automation-in-Standard-ML)

</div>

> **MSc dissertation (University of Sheffield · Supervisor: Gergely Buday).** An Ansible-inspired automation framework with **role-based access control enforced at the type-system level** in Standard ML. The functional type system and exhaustive pattern matching verify security policy **at compile time** — making illegal states unrepresentable and giving mathematical guarantees of **default-deny** that dynamically typed automation tools struggle to provide.

**🎯 Key contributions**
- 🔒 **Least-privilege RBAC core** with explicit policy versioning and default-deny by construction
- 🧠 **Explainable authorisation** — every ALLOW/DENY carries a human-readable rationale (role, permission, policy version, reasoning)
- 🧾 **Tamper-evident, reproducible audit artifacts** with checksum integrity for verification
- 🖥️ **Cross-platform** operational playbooks (system audit, guest denial, service maintenance, report aggregation) running uniformly across **Windows · macOS · Linux** behind one OS-agnostic interface
- ✅ Validated with **golden tests** for enforcement logic and playbook behaviour

`Standard ML` `RBAC` `Default-Deny` `Decision Explainability` `Auditability` `Cross-Platform` `Functional Security`

---

## 🧰 Arsenal

<div align="center">

**Detection · SIEM · SOC**

![Microsoft Sentinel](https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Defender](https://img.shields.io/badge/Microsoft%20Defender-00A4EF?style=for-the-badge&logo=microsoft&logoColor=white)
![KQL](https://img.shields.io/badge/KQL-2962FF?style=for-the-badge&logo=azuredataexplorer&logoColor=white)
![Wazuh](https://img.shields.io/badge/Wazuh-3A86FF?style=for-the-badge&logo=wazuh&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-E02041?style=for-the-badge&logo=mitre&logoColor=white)

**Offensive · Recon**

![Kali](https://img.shields.io/badge/Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp%20Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white)
![Nmap](https://img.shields.io/badge/Nmap-4682B4?style=for-the-badge&logo=nmap&logoColor=white)
![Cowrie](https://img.shields.io/badge/Cowrie%20Honeypot-1f6f43?style=for-the-badge)
![Recon](https://img.shields.io/badge/subfinder%20%C2%B7%20httpx%20%C2%B7%20nuclei-3DDC84?style=for-the-badge&logo=go&logoColor=white)

**Languages**

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![Standard ML](https://img.shields.io/badge/Standard%20ML-DD0031?style=for-the-badge)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white)

**Cloud · Infra · Tooling**

![Azure](https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05033?style=for-the-badge&logo=git&logoColor=white)
![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white)

</div>

---

## 🎓 Education & Certifications

<div align="center">

🏛️ **MSc Cybersecurity & Artificial Intelligence** — University of Sheffield, UK *(NCSC-certified programme)*

| 🏅 Certification | 🏢 Issuer | 📌 Status |
|------------------|-----------|-----------|
| **CompTIA Security+** | CompTIA | ✅ Certified |
| **Microsoft SC-900** — Security, Compliance & Identity Fundamentals | Microsoft | ✅ Certified |
| **Microsoft AZ-900** — Azure Fundamentals | Microsoft | ✅ Certified |
| **eJPT** — Junior Penetration Tester | INE / eLearnSecurity | 🔄 In Progress |
| **SC-200** — Security Operations Analyst | Microsoft | 🎯 Planned (Next) |

</div>

---

## 📊 GitHub Stats

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=themodernhacker&show_icons=true&include_all_commits=true&count_private=true&hide_border=true&title_color=00F260&icon_color=00F260&text_color=c9d1d9&bg_color=0D1117" />
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=themodernhacker&layout=compact&hide_border=true&title_color=00F260&text_color=c9d1d9&bg_color=0D1117&langs_count=8" />

<br/>

<img src="https://streak-stats.demolab.com?user=themodernhacker&hide_border=true&background=0D1117&stroke=00F260&ring=00F260&fire=00F260&currStreakNum=00F260&currStreakLabel=00F260&sideNums=c9d1d9&sideLabels=c9d1d9&dates=8b949e" />

</div>

---

## 🏆 Trophies

<div align="center">

<img src="https://github-profile-trophy.vercel.app/?username=themodernhacker&theme=matrix&no-frame=true&no-bg=true&margin-w=4&column=7" />

</div>

---

## 📈 Contribution Activity

<div align="center">

<img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=themodernhacker&bg_color=0D1117&color=00F260&line=00F260&point=ffffff&area=true&hide_border=true" />

</div>

## 🐍 Contribution Snake

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/themodernhacker/themodernhacker/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/themodernhacker/themodernhacker/output/github-contribution-grid-snake.svg">
  <img alt="github contribution snake" src="https://raw.githubusercontent.com/themodernhacker/themodernhacker/output/github-contribution-grid-snake.svg">
</picture>

</div>

---

<div align="center">

### 💭 `cat /dev/wisdom`

![Quote](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=tokyonight)

<br/>

⭐ *If a project here is useful to you, a star helps more than you'd think.*

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,2,5,30&height=120&section=footer" />

</div>
