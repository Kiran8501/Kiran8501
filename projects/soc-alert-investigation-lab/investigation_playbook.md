# Investigation Playbook

## Scenario

The synthetic records show repeated failed authentication attempts for `alex.lee`, followed by a successful login, DNS activity, and an allowed outbound network event from host `WS-014`. Determine whether the evidence supports escalation and identify the gaps that prevent a firm conclusion.

## Triage checklist

- [ ] Confirm the alert timestamp and time zone.
- [ ] Identify the affected account, host, source IP, and destination IP.
- [ ] Check whether authentication failures are clustered in a short interval.
- [ ] Confirm whether a success followed the failures and whether MFA was used.
- [ ] Compare the activity with normal user behavior and known maintenance windows.
- [ ] Review DNS and network events in the same time window.
- [ ] Request endpoint process, EDR, VPN, identity-provider, proxy, and firewall context where available.
- [ ] Determine whether outbound volume is unusual for this host and application.
- [ ] Document evidence, competing explanations, confidence, and next actions.

## Exercise tasks

1. Run the failed-authentication SPL query and record the matching event IDs.
2. Create a timeline from 09:00–09:10 UTC on 20 October 2026.
3. Explain what the successful authentication does and does not prove.
4. Identify the missing telemetry needed to attribute the outbound connection to a process or user action.
5. Assign a provisional severity using your organization's rubric; if no rubric is supplied, state the assumptions.
6. Draft an incident report using the template.
7. Suggest a detection improvement that reduces false positives, such as grouping by account/source and requiring additional context before escalation.

## Evidence versus interpretation

**Observed in the sample:** three authentication failures are followed by a success for the same account and source address. Later, the same host has a DNS query and an allowed outbound network event.

**Not established by these records:** account compromise, malware execution, malicious destination, sensitive data access, or successful data exfiltration. The sample does not include process lineage, MFA outcome, destination reputation, file access, or data classification.

## Escalation considerations

Escalate for further investigation if the source is unexpected, the user denies the activity, MFA or identity logs show anomalies, endpoint telemetry indicates suspicious execution, or the destination/transfer conflicts with approved business activity. Follow organizational incident-response procedures and preserve evidence according to policy.

## Lab completion criteria

- Searches execute successfully against the sample data.
- Findings cite event IDs and timestamps.
- The report separates facts from hypotheses.
- Confidence and limitations are explicit.
- Recommendations are actionable and proportionate.
