# SOC Investigation Report

## 1. Case details

- **Case ID:** SOC-LAB-001
- **Analyst:** [Your name]
- **Date/time opened:** [UTC timestamp]
- **Data source and time range:** [Index/source, start, end]
- **Status:** [Open / Monitoring / Closed]
- **Provisional severity:** [Informational / Low / Medium / High / Critical, with rationale]

## 2. Executive summary

[Summarize the alert, what was confirmed, and what remains uncertain in 3–5 sentences.]

## 3. Trigger and scope

- **Triggering behavior:** [What prompted review?]
- **Account(s):** [Account or unknown]
- **Host(s):** [Host or unknown]
- **Source/destination:** [Relevant IPs/domains]
- **Scope limitations:** [Data not available, time gaps, parsing concerns]

## 4. Timeline

| Time (UTC) | Event ID | Observation | Interpretation / caveat |
|---|---|---|---|
| [timestamp] | [ID] | [Observed event] | [Supported interpretation and uncertainty] |

## 5. Evidence collected

| Evidence ID | Source/search | Result | Relevance |
|---|---|---|---|
| E-01 | [SPL query or source] | [Concise result] | [Why it matters] |

Include the exact SPL, time range, result count, and screenshot/export reference where appropriate. Do not include sensitive production data in a public portfolio.

## 6. Assessment

- **Confirmed facts:** [Directly supported by evidence]
- **Working hypothesis:** [Potential explanation]
- **Alternative explanations:** [Benign or other plausible causes]
- **Confidence:** [Low / Medium / High, with explanation]
- **MITRE ATT&CK mapping:** [Technique and ID only if evidence supports it]

## 7. Impact and severity rationale

[Describe known impact. If impact is unknown, say so. Explain severity based on the applicable rubric and evidence.]

## 8. Recommended actions

1. [Immediate validation or containment action, if warranted]
2. [Additional telemetry or owner confirmation required]
3. [Remediation or control improvement]
4. [Post-action validation and monitoring]

Follow approved incident-response and evidence-preservation procedures. Do not isolate systems or disable accounts without appropriate authorization.

## 9. Closure criteria

[State what evidence or approval is needed to close, downgrade, or escalate the case.]

## 10. Lessons learned

[Detection tuning, logging gaps, false-positive reduction, and follow-up tasks.]
