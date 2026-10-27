# SOC Alert Investigation Lab

A beginner-friendly, defensive SOC portfolio project using **synthetic security events** to practice alert triage, Splunk searches, evidence-based analysis, and incident reporting.

> **Lab status:** Documentation and sample data are provided for learning. The included events are synthetic—not collected from a real organization—and the example conclusions are hypotheses to validate during the exercise. No production system is involved.

## Objectives

- Investigate repeated authentication failures followed by a successful login.
- Review DNS and outbound network events for contextual indicators.
- Use SPL to filter, aggregate, and correlate sample events.
- Build a concise, evidence-based incident timeline.
- Record confidence, limitations, and practical response recommendations.

## Repository contents

| File | Purpose |
|---|---|
| `sample_logs.csv` | Synthetic authentication, DNS, and network events |
| `splunk_queries.md` | SPL searches to run after importing the CSV |
| `investigation_playbook.md` | Triage process, evidence checklist, and lab tasks |
| `incident_report_template.md` | Reusable report format for documenting findings |

## Lab scenario

A fictional employee account has several failed authentication attempts followed by a successful login. Around the same investigation window, DNS and network records provide additional context. Determine what the sample telemetry supports, what remains uncertain, and what additional evidence you would request.

**Do not assume compromise from failed logins alone.** Consider the source, timing, successful authentication context, user verification, endpoint telemetry, and whether the network events can be tied to the same host or identity.

## Run the lab in Splunk

1. Download `sample_logs.csv`.
2. In a local Splunk instance, create or select a lab index such as `soc_lab`.
3. Upload the CSV as a lookup or ingest it as event data. If ingesting it, configure CSV field extraction and a timestamp field suitable for your Splunk version.
4. Run the searches in `splunk_queries.md`, adjusting the index and field names to match your setup.
5. Complete the tasks in `investigation_playbook.md`.
6. Write your findings using `incident_report_template.md`.

The sample data uses UTC timestamps and fields including `timestamp`, `event_type`, `user`, `src_ip`, `dest_ip`, `host`, `action`, `domain`, `bytes_out`, and `details`.

## Expected deliverables

- Screenshots or exported results of relevant SPL searches (use only synthetic lab data).
- A short timeline with event IDs and timestamps.
- A finding statement that separates observed evidence from interpretation.
- Severity rationale, confidence level, limitations, and recommended next steps.

## MITRE ATT&CK

Map behavior to ATT&CK only when the evidence supports it. Repeated authentication attempts may warrant review of **Brute Force (T1110)**, but the synthetic scenario is not proof that a real technique occurred. Include the technique ID and rationale in your report only if justified by the investigation.

## Safety and quality notes

- Use this project only in a local or otherwise authorized environment.
- Do not add real credentials, personal data, private logs, or customer information.
- Do not label an event malicious without supporting context.
- Do not claim the searches were run or the incident was confirmed unless you actually performed and documented those steps.

## Skills demonstrated

Splunk/SPL fundamentals, log analysis, alert triage, event correlation, incident documentation, network-security concepts, and evidence-based reasoning.
