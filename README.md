<!--
Profile README for https://github.com/Kiran8501
Keep claims aligned with projects and experience that can be demonstrated in repositories.
-->

<h1 align="center">Sai Kiran Ande</h1>
<h3 align="center">Cybersecurity Analyst | SOC Operations | Threat Detection & Network Forensics</h3>

<p align="center">
  <a href="https://github.com/Kiran8501">
    <img src="https://img.shields.io/badge/GitHub-Kiran8501-181717?style=for-the-badge&logo=github" alt="GitHub profile" />
  </a>
  <img src="https://img.shields.io/badge/Focus-SOC%20%26%20Defensive%20Security-0A66C2?style=for-the-badge" alt="SOC and defensive security" />
  <img src="https://img.shields.io/badge/Research-Explainable%20ML-6A5ACD?style=for-the-badge" alt="Explainable machine learning" />
</p>

## Professional Profile

Cybersecurity postgraduate with SOC internship experience and a computer science background, focused on security operations, SIEM monitoring, alert triage, network traffic analysis, vulnerability assessment, and incident investigation.

My investigation approach is evidence-driven: validate an alert against available telemetry, establish a timeline, assess likely impact, document supporting evidence, and recommend remediation. This portfolio highlights practical labs, security tooling, and research with clear scope and reproducible steps.

## Technical Toolkit

| Area | Technologies and technical focus |
|---|---|
| SOC operations & SIEM | Splunk, event/log analysis, alert triage, investigation notes |
| Network security | Wireshark, Nmap, TCP/IP fundamentals, packet and traffic analysis |
| Vulnerability assessment | OpenVAS, vulnerability identification, risk-aware reporting |
| Web application security | Burp Suite, request/response inspection, authorized testing |
| Security testing labs | Kali Linux, Metasploit Framework, controlled lab environments |
| Scripting & data handling | Python, Pandas, NumPy |
| Machine learning | Scikit-learn, Logistic Regression, binary classification, evaluation metrics |
| Explainable AI | SHAP, feature importance, record-level prediction explanations |
| Research workflow | CICIDS2017, data cleaning, encoding, feature preparation, scaling, confusion-matrix analysis |

## SOC Investigation Workflow

The workflow I aim to demonstrate in lab documentation is:

1. **Alert intake** — record the alert source, timestamp, affected asset, and reason for investigation.
2. **Evidence collection** — review relevant SIEM events, authentication records, endpoint/network telemetry, and packet captures when available.
3. **Triage and validation** — compare event context, timestamps, source/destination details, and related activity to distinguish suspicious behavior from benign activity.
4. **Scoping and timeline** — identify related events and summarize the sequence of observed activity without assuming facts not supported by logs.
5. **MITRE ATT&CK mapping** — map behavior to a technique only when the evidence supports that interpretation.
6. **Response and reporting** — document severity rationale, evidence, limitations, recommended containment, remediation, and follow-up checks.

> This is a learning and documentation framework, not a claim that every step has been automated or performed in a production SOC.

## Research Project: Explainable Data Exfiltration Forensics

**Research title:** *An Explainable and Adaptive Multi-Model Learning Framework for Generalized Data Exfiltration Forensics*

- Dataset: CICIDS2017 network traffic benchmark.
- Preprocessing: data cleaning, label encoding, feature preparation, and scaling.
- Implemented classifier: **Logistic Regression** for binary classification.
- Explainability: **SHAP (SHapley Additive Explanations)** for feature-importance analysis and explanations of individual predictions.
- Evaluation: accuracy, precision, recall, F1 score, and confusion-matrix analysis.
- Tools: Python, Pandas, NumPy, Scikit-learn, Matplotlib, SHAP, and Jupyter Notebook.

**Scope and limitations:** The adaptive multi-model framework is a proposed future direction. The implemented research used Logistic Regression as the primary model. Findings should be interpreted within the dataset, preprocessing choices, class distribution, and experimental environment; benchmark performance alone does not establish production readiness.

## Practical Security Experience

### SOC Internship

Internship exposure to security and network tools including Splunk, Nmap, OpenVAS, Wireshark, Burp Suite, Metasploit Framework, and Kali Linux.

I am continuing to build repeatable investigation practice through lab exercises and written analysis. Tool exposure does not imply advanced proficiency or production ownership of every tool.

## Portfolio Projects

- **SOC Alert Investigation Lab** — [Open project](https://github.com/Kiran8501/Kiran8501/tree/main/projects/soc-alert-investigation-lab). Includes synthetic authentication/DNS/network events, SPL searches, a triage playbook, and an incident report template. Lab data is synthetic; complete the searches and document your own results before claiming hands-on execution.
- **Image Forgery Detection** — [View repository](https://github.com/Kiran8501/Image-forgery-detection). Refer to the repository code and documentation for verified implementation details.
- **Data Exfiltration Forensics** — research project described above. A dedicated code repository can be linked here when its implementation is published.

## Education

- **M.Tech, Cybersecurity** — completed August 2026
- **B.Tech, Computer Science and Engineering** — 2019–2023

## Current Technical Learning Goals

- Improve SPL searches for filtering, aggregation, time-based analysis, and alert investigation.
- Practice network protocol analysis and correlation of events across available logs.
- Build Python utilities for parsing and summarizing security events, with tests and documented limitations.
- Learn to map validated findings to relevant MITRE ATT&CK techniques.
- Produce concise incident reports with evidence, impact, confidence, and actionable remediation.

## Security and Documentation Principles

- Test only systems and environments where authorization is explicit.
- Use synthetic or sanitized data in public demonstrations.
- Never publish credentials, private logs, or sensitive incident information.
- Document assumptions, reproducible steps, limitations, and remediation.
- Prefer verifiable evidence over unsupported claims.

## Connect

- **GitHub:** [Kiran8501](https://github.com/Kiran8501)

<p align="center">
  <i>Building practical, explainable, and evidence-driven cybersecurity skills.</i>
</p>
