<!-- ====================== HEADER ====================== -->
<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,2,5,30&height=230&section=header&text=The%20Modern%20Hacker&fontSize=55&fontColor=ffffff&animation=twinkling&fontAlignY=36&desc=Abhishek%20K.%20Sahu%20%E2%80%A2%20Cyber%20Security%20Analyst%20%7C%20SOC%20%C2%B7%20Detection%20Engineering%20%C2%B7%20Security%20Automation&descAlignY=56&descAlign=50" />

<a href="https://github.com/themodernhacker">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=00F260&center=true&vCenter=true&width=820&lines=Cyber+Security+Analyst+%7C+SOC+%26+Detection+Engineering+%F0%9F%9B%A1;MSc+Cybersecurity+%26+AI+%7C+University+of+Sheffield;Wazuh+%7C+Microsoft+Sentinel+%7C+KQL+%7C+MITRE+ATT%26CK;Detect+%E2%86%92+Investigate+%E2%86%92+Automate%2C+tested+end+to+end;CompTIA+Security%2B+%7C+SC-900+%7C+AZ-900;I+build+the+detection%2C+then+build+the+test+that+proves+it+works" alt="Typing SVG" />
</a>

<br/>

[![Website](https://img.shields.io/badge/Portfolio-themodernhacker.com-00F260?style=for-the-badge&logo=firefox&logoColor=black)](https://themodernhacker.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/themodernhacker)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:heysahuabhi@gmail.com)
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://twitter.com/themodernhacker)
[![Medium](https://img.shields.io/badge/Medium-000000?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@themodernhacker)

<img src="https://komarev.com/ghpvc/?username=themodernhacker&label=Profile+Views&color=00F260&style=flat-square" alt="Profile views" />
<img src="https://img.shields.io/badge/Right%20to%20Work-UK%20Graduate%20Visa-00F260?style=flat-square" alt="Right to work" />
<img src="https://img.shields.io/badge/Status-Enhanced%20DBS-00F260?style=flat-square" alt="DBS" />

</div>

---

## `whoami`

```bash
┌──(abhi㉿themodernhacker)-[~]
└─$ whoami --full

  NAME         : Abhishek Kumar Sahu   (aka "The Modern Hacker")
  ROLE         : Cyber Security Analyst  |  SOC · Detection Engineering · Security Automation
  EDUCATION    : MSc Cybersecurity & Artificial Intelligence — University of Sheffield (NCSC-certified)
  LOCATION     : United Kingdom  🇬🇧   (Graduate Visa · Full Right to Work · Enhanced DBS)
  FOCUS        : Threat Detection · SIEM Engineering · Incident Response · Security Automation
  CORE STACK   : Wazuh · Microsoft Sentinel · KQL · MITRE ATT&CK · NIST SP 800-61 · Python
  IN PROGRESS  : eJPT  →  next: SC-200 (Security Operations Analyst)
  MINDSET      : "Every detection ships with a test. Every incident gets a write-up. Every claim is checkable."
```

---

## ⚔️ Featured Projects — Detect → Investigate → Automate

Three connected projects that mirror how a real SOC actually works. All built on
the same lab, all cross-linked, all fully tested.

<div align="center">

### 🍯 honeypot-siem — Detection

[![Repo](https://img.shields.io/badge/GitHub-honeypot--siem-00F260?style=for-the-badge&logo=github&logoColor=black)](https://github.com/themodernhacker/honeypot-siem)
[![Wazuh](https://img.shields.io/badge/SIEM-Wazuh%204.9-2962FF?style=for-the-badge)](https://github.com/themodernhacker/honeypot-siem)
[![MITRE](https://img.shields.io/badge/Mapped%20to-MITRE%20ATT%26CK-E02041?style=for-the-badge)](https://github.com/themodernhacker/honeypot-siem)

</div>

> A live Cowrie honeypot behind a tuned Wazuh SIEM — every alert mapped to
> MITRE ATT&CK, every rule backed by a test. **Attack it → detect it → prove it.**

**🎯 What it demonstrates**
- ✍️ **12 custom Wazuh detection rules** + **5 Microsoft Sentinel KQL queries**, mapped to **9 MITRE ATT&CK techniques across 6 tactics**
- 🔗 Context-aware escalation: recon following a confirmed compromise auto-escalates severity, not just standalone commands
- 🧪 A **detection-as-code test suite** that caught a real correlation-rule bug before it shipped — documented honestly, including the fix
- 📝 A tuning / false-positive write-up covering how each rule would be tuned in production, not just how it fires in the lab

| Detection | MITRE ATT&CK | Severity |
|-----------|:------------:|:--------:|
| SSH brute force (8+ fails, one source) | `T1110` | 🔴 High |
| Successful login **after** brute force (compromise) | `T1078` + `T1110` | 🔴 Critical |
| Post-access recon (`uname`, `id`, `whoami`) | `T1082` / `T1033` | 🟠 Medium |
| Recon **following a confirmed compromise** (context escalation) | `T1082` / `T1033` | 🔴 Critical |
| Second-stage payload pull (`wget` / `curl`) | `T1105` | 🔴 High |
| Rapid automated connections | `T1046` | 🟡 Low |

`Cowrie` `Wazuh 4.9` `Microsoft Sentinel` `KQL` `Docker Compose` `Python` `MITRE ATT&CK`

---

<div align="center">

### 📋 incident-investigation-report — Investigation

[![Repo](https://img.shields.io/badge/GitHub-incident--investigation--report-00F260?style=for-the-badge&logo=github&logoColor=black)](https://github.com/themodernhacker/incident-investigation-report)
[![NIST](https://img.shields.io/badge/Framework-NIST%20SP%20800--61-2962FF?style=for-the-badge)](https://github.com/themodernhacker/incident-investigation-report)

</div>

> The companion to `honeypot-siem` — same lab, same rules, but the analyst-facing
> deliverable instead of the detection engineering. A full incident investigation
> built from a **live captured attack**, not a canned dataset.

**🎯 What it demonstrates**
- 📐 Structured on the **NIST SP 800-61** incident-response lifecycle — the framework UK SOC/IR postings reference by name
- 🔍 A timeline **cross-verified line-by-line against the raw logs**, not paraphrased from memory
- 🧾 IOC extraction, impact assessment, and a containment/recovery plan written as one coherent response, not fragmented technique notes
- 🎫 A short-form incident ticket alongside the full report — the two formats a real SOC actually produces

`NIST SP 800-61` `Incident Response` `Log Analysis` `Digital Forensics` `MITRE ATT&CK`

---

<div align="center">

### ⚙️ soar-triage — Automation

[![Repo](https://img.shields.io/badge/GitHub-soar--triage-00F260?style=for-the-badge&logo=github&logoColor=black)](https://github.com/themodernhacker/soar-triage)
[![SOAR](https://img.shields.io/badge/Type-Security%20Automation-2962FF?style=for-the-badge)](https://github.com/themodernhacker/soar-triage)

</div>

> The step almost no junior portfolio shows: the automated first-response
> between "an alert fires" and "someone acts on it." Event-driven, not polled —
> hooks directly into Wazuh's native integration mechanism.

**🎯 What it demonstrates**
- ⚡ **Enrich → triage → ticket**, fully automated: classifies IOCs, applies an explainable (non-black-box) triage rule set, and auto-files real **GitHub Issues** via the REST API
- 📊 **Measured, not estimated:** ~170 seconds doing the same triage by hand vs. **~0.7 seconds automated**, across 11 live alerts in one run — full timestamped trace committed as evidence
- 🔐 Credential hygiene done properly: fine-scoped token, `.env` gitignored from the first commit, verified clean across full git history
- 🧪 Detection-as-code again — triage logic unit tested with zero live API calls required

`Python` `Wazuh Integrations` `GitHub REST API` `SOAR` `Security Automation` `AbuseIPDB`

---

## 🔬 Other Work

<div align="center">

### 🛡️ Ansible-Inspired RBAC Security Automation in Standard ML

[![Repo](https://img.shields.io/badge/GitHub-RBAC--Automation--SML-00F260?style=for-the-badge&logo=github&logoColor=black)](https://github.com/themodernhacker/Ansible-like-RBAC-Automation-in-Standard-ML)
[![Type](https://img.shields.io/badge/MSc-Dissertation-7D2196?style=for-the-badge)](https://github.com/themodernhacker/Ansible-like-RBAC-Automation-in-Standard-ML)

</div>

> MSc dissertation (University of Sheffield). Role-based access control enforced
> at the type-system level in Standard ML — illegal states unrepresentable,
> default-deny by construction, every decision explainable and auditable.

`Standard ML` `RBAC` `Default-Deny` `Auditability`

*(Details on this one weren't re-checked in this pass — see the repo itself for the current state.)*

---

## 🧰 Arsenal

<div align="center">

**Detection · SIEM · SOC** *(daily-driver tools, deepest hands-on experience)*

![Wazuh](https://img.shields.io/badge/Wazuh-3A86FF?style=for-the-badge&logo=wazuh&logoColor=white)
![Microsoft Sentinel](https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![KQL](https://img.shields.io/badge/KQL-2962FF?style=for-the-badge&logo=azuredataexplorer&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-E02041?style=for-the-badge&logo=mitre&logoColor=white)
![NIST](https://img.shields.io/badge/NIST%20SP%20800--61-004B87?style=for-the-badge)

**Automation · Scripting**

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)

**Security Testing** *(hands-on, supporting skills)*

![Burp Suite](https://img.shields.io/badge/Burp%20Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white)
![Nessus](https://img.shields.io/badge/Nessus-00A9E0?style=for-the-badge)
![Caido](https://img.shields.io/badge/Caido-6E56CF?style=for-the-badge)

**Cloud · Infra · Tooling**

![Azure](https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05033?style=for-the-badge&logo=git&logoColor=white)

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
| **TryHackMe — SOC Level 1** | TryHackMe | ✅ Completed |
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

⭐ *If a project here is useful to you, a star helps more than you'd think.*

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,2,5,30&height=120&section=footer" />

</div>
