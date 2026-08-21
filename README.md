<!-- ============================ HEADER ============================ -->
<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0D2E5C&height=190&section=header&text=Abhishek%20Kumar%20Sahu&fontSize=44&fontColor=ffffff&fontAlignY=40&desc=Cyber%20Security%20Analyst%20%C2%B7%20SOC%20%C2%B7%20Detection%20Engineering%20%C2%B7%20Security%20Automation&descSize=16&descAlignY=60&animation=fadeIn" alt="Abhishek Kumar Sahu — Cyber Security Analyst" />

<a href="https://github.com/themodernhacker">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=21&pause=1200&color=2F81F7&center=true&vCenter=true&width=780&lines=Cyber+Security+Analyst+%7C+SOC+%26+Detection+Engineering;MSc+Cybersecurity+%26+AI+%7C+University+of+Sheffield;Wazuh+%C2%B7+Microsoft+Sentinel+%C2%B7+KQL+%C2%B7+MITRE+ATT%26CK;Detect+%E2%86%92+Investigate+%E2%86%92+Automate%2C+tested+end+to+end;Every+detection+ships+with+a+test+that+proves+it+works" alt="Typing SVG" />
</a>

<br/><br/>

[![Portfolio](https://img.shields.io/badge/Portfolio-themodernhacker.com-2F81F7?style=for-the-badge&logo=firefoxbrowser&logoColor=white)](https://themodernhacker.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/themodernhacker)
[![Email](https://img.shields.io/badge/Email-333333?style=for-the-badge&logo=gmail&logoColor=white)](mailto:heysahuabhi@gmail.com)
[![Medium](https://img.shields.io/badge/Medium-333333?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@themodernhacker)

<br/>

![Right to work](https://img.shields.io/badge/Right%20to%20Work-UK%20Graduate%20Visa-1F6FEB?style=flat-square)
![DBS](https://img.shields.io/badge/Clearance-Enhanced%20DBS-1F6FEB?style=flat-square)
![Location](https://img.shields.io/badge/Based%20in-United%20Kingdom-1F6FEB?style=flat-square)
<img src="https://komarev.com/ghpvc/?username=themodernhacker&label=Profile%20views&color=1F6FEB&style=flat-square" alt="Profile views" />

</div>

---

## About

```text
$ whoami

  Name        Abhishek Kumar Sahu  (themodernhacker)
  Role        Cyber Security Analyst — SOC, Detection Engineering, Security Automation
  Education   MSc Cybersecurity & AI, University of Sheffield  (NCSC-certified programme)
  Location    United Kingdom  ·  Graduate Visa, full right to work  ·  Enhanced DBS
  Focus       Threat detection · SIEM engineering · Incident response · SOC automation
  Stack       Wazuh · Microsoft Sentinel · KQL · MITRE ATT&CK · NIST SP 800-61 · Python
  Next        eJPT (in progress)  ->  SC-200 Security Operations Analyst
  Approach    Every detection ships with a test. Every incident gets a write-up.
              Every claim is checkable.
```

I build the detection, then build the test that proves it works. My portfolio is
one connected story that mirrors a real SOC: **detect an attack, investigate it,
then automate the first response** — all on the same lab, all cross-linked, all
backed by evidence a reviewer can verify.

---

## Featured Projects

> A three-part SOC workflow on one honeypot lab. **Detect → Investigate → Automate.**

### `honeypot-siem` · Detection

[![Repo](https://img.shields.io/badge/View%20Repository-honeypot--siem-2F81F7?style=for-the-badge&logo=github&logoColor=white)](https://github.com/themodernhacker/honeypot-siem)

A live Cowrie SSH honeypot behind a tuned Wazuh SIEM. Every alert is mapped to
MITRE ATT&CK, and every rule is backed by a test. **Attack it, detect it, prove it.**

- **12 custom Wazuh rules + 5 Microsoft Sentinel KQL queries**, mapped to **9 ATT&CK techniques across 6 tactics**
- **Context-aware escalation:** recon *following a confirmed compromise* auto-escalates severity, rather than alerting on standalone commands
- A **detection-as-code test suite** that caught a real correlation-rule bug before it shipped, documented honestly with the fix
- A tuning / false-positive write-up: how each rule would be tuned in production, not just how it fires in the lab

| Detection | ATT&CK | Severity |
|-----------|:------:|:--------:|
| SSH brute force (8+ fails, one source) | `T1110` | High |
| Successful login **after** brute force (compromise) | `T1078` · `T1110` | Critical |
| Recon **following a confirmed compromise** (context escalation) | `T1082` · `T1033` | Critical |
| Second-stage payload pull (`wget` / `curl`) | `T1105` | High |
| Rapid automated connections | `T1046` | Low |

<sub>`Cowrie` · `Wazuh 4.9` · `Microsoft Sentinel` · `KQL` · `Docker` · `Python` · `MITRE ATT&CK`</sub>

### `incident-investigation-report` · Investigation

[![Repo](https://img.shields.io/badge/View%20Repository-incident--investigation--report-2F81F7?style=for-the-badge&logo=github&logoColor=white)](https://github.com/themodernhacker/incident-investigation-report)

The analyst-facing companion to the detection work: a full incident investigation
built from a **live captured attack**, not a canned dataset.

- Structured on the **NIST SP 800-61** incident-response lifecycle, the framework UK SOC/IR roles reference by name
- A timeline **cross-verified line-by-line against the raw logs**, not paraphrased from memory
- IOC extraction, impact assessment, and a single coherent containment / recovery plan
- A short-form incident ticket alongside the full report, the two formats a real SOC produces

<sub>`NIST SP 800-61` · `Incident Response` · `Log Analysis` · `Digital Forensics` · `MITRE ATT&CK`</sub>

### `soar-triage` · Automation

[![Repo](https://img.shields.io/badge/View%20Repository-soar--triage-2F81F7?style=for-the-badge&logo=github&logoColor=white)](https://github.com/themodernhacker/soar-triage)

The step most junior portfolios skip: the automated first response between *an
alert fires* and *someone acts on it*. Event-driven, hooked into Wazuh's native
integration mechanism, not polling.

- **Enrich → triage → ticket**, fully automated: classifies the source, applies an explainable (non-black-box) rule set, and auto-files real **GitHub Issues** via the REST API
- **Measured, not estimated:** ~170 s to triage by hand vs. **~0.7 s automated**, across 11 live alerts, with the full timestamped trace committed as evidence
- Credential hygiene done properly: fine-scoped token, `.env` gitignored from the first commit, verified clean across git history
- Triage logic unit-tested with zero live API calls required

<sub>`Python` · `Wazuh Integrations` · `GitHub REST API` · `SOAR` · `AbuseIPDB`</sub>

---

## Other Work

### `RBAC Security Automation in Standard ML` · MSc Dissertation

[![Repo](https://img.shields.io/badge/View%20Repository-RBAC--Automation--SML-2F81F7?style=for-the-badge&logo=github&logoColor=white)](https://github.com/themodernhacker/Ansible-like-RBAC-Automation-in-Standard-ML)

MSc dissertation, University of Sheffield: an Ansible-inspired role-based access
control system enforced at the **type-system level** in Standard ML, so illegal
states are unrepresentable, access is **default-deny by construction**, and every
decision is explainable and auditable.

<sub>`Standard ML` · `RBAC` · `Default-Deny` · `Type Safety` · `Auditability`</sub>

---

## Skills & Tooling

**Detection · SIEM · SOC**

![Wazuh](https://img.shields.io/badge/Wazuh-3A86FF?style=flat-square&logo=wazuh&logoColor=white)
![Microsoft Sentinel](https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=flat-square&logo=microsoft&logoColor=white)
![KQL](https://img.shields.io/badge/KQL-2F81F7?style=flat-square&logo=azuredataexplorer&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-C7253E?style=flat-square)
![NIST 800-61](https://img.shields.io/badge/NIST%20SP%20800--61-004B87?style=flat-square)

**Automation · Scripting**

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

**Security Testing**

![Burp Suite](https://img.shields.io/badge/Burp%20Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white)
![Nessus](https://img.shields.io/badge/Nessus-00A9E0?style=flat-square)
![Caido](https://img.shields.io/badge/Caido-6E56CF?style=flat-square)

**Cloud · Infrastructure**

![Azure](https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05033?style=flat-square&logo=git&logoColor=white)

---

## Education & Certifications

**MSc Cybersecurity & Artificial Intelligence** — University of Sheffield, UK *(NCSC-certified programme)*

| Certification | Issuer | Status |
|---------------|--------|--------|
| CompTIA Security+ | CompTIA | Certified |
| Microsoft SC-900 — Security, Compliance & Identity | Microsoft | Certified |
| Microsoft AZ-900 — Azure Fundamentals | Microsoft | Certified |
| TryHackMe — SOC Level 1 | TryHackMe | Completed |
| eJPT — Junior Penetration Tester | INE / eLearnSecurity | In progress |
| SC-200 — Security Operations Analyst | Microsoft | Planned (next) |

---

## GitHub Activity

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=themodernhacker&show_icons=true&include_all_commits=true&count_private=true&hide_border=true&title_color=2F81F7&icon_color=2F81F7&text_color=c9d1d9&bg_color=0D1117" alt="GitHub stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=themodernhacker&layout=compact&hide_border=true&title_color=2F81F7&text_color=c9d1d9&bg_color=0D1117&langs_count=8" alt="Top languages" />

<img width="92%" src="https://github-readme-activity-graph.vercel.app/graph?username=themodernhacker&bg_color=0D1117&color=2F81F7&line=2F81F7&point=ffffff&area=true&hide_border=true" alt="Contribution activity" />

</div>

---

<div align="center">
<sub>Detection → Investigation → Automation · built on one lab · every claim checkable.</sub>
</div>
