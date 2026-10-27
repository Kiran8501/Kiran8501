# Splunk SPL Queries — SOC Alert Investigation Lab

These examples assume the CSV was ingested into `index=soc_lab` and that fields were extracted. Adapt the index, timestamp configuration, and field names to your lab. Run against the provided synthetic events only.

## 1. Inspect available events

```spl
index=soc_lab
| sort 0 timestamp
| table timestamp event_id event_type user src_ip dest_ip host action domain bytes_out details
```

## 2. Count failed authentications by account and source

```spl
index=soc_lab event_type=authentication action=failure
| stats count as failed_attempts min(timestamp) as first_seen max(timestamp) as last_seen by user src_ip host
| sort - failed_attempts
```

## 3. Find successful logins following repeated failures

This search summarizes events by account/source. It is a triage lead, not proof that the same person performed all attempts.

```spl
index=soc_lab event_type=authentication
| eval failed=if(action="failure",1,0), successful=if(action="success",1,0)
| stats sum(failed) as failures sum(successful) as successes values(host) as hosts values(action) as actions min(timestamp) as first_seen max(timestamp) as last_seen by user src_ip
| where failures >= 3 AND successes >= 1
| sort - failures
```

## 4. Review outbound network volume by host and user

```spl
index=soc_lab event_type=network action=allowed
| stats sum(bytes_out) as total_bytes_out count as connections values(dest_ip) as destinations by user host
| sort - total_bytes_out
```

## 5. Build a chronological view for one account

```spl
index=soc_lab user="alex.lee"
| sort 0 timestamp
| table timestamp event_id event_type action src_ip dest_ip host domain bytes_out details
```

## 6. Inspect DNS activity

```spl
index=soc_lab event_type=dns
| stats count as queries values(domain) as domains values(dest_ip) as dns_servers by user host src_ip
```

## 7. Correlate events by host in a short time window

```spl
index=soc_lab
| eval event_time=strptime(timestamp,"%Y-%m-%dT%H:%M:%SZ")
| sort 0 host event_time
| streamstats current=f last(event_time) as previous_event_time last(event_type) as previous_event_type by host
| eval gap_seconds=event_time-previous_event_time
| table timestamp host user event_type action src_ip dest_ip domain bytes_out previous_event_type gap_seconds details
```

Check your Splunk timestamp parsing and field extraction before interpreting this output.

## Interpretation cautions

- The IP ranges in the CSV are reserved for documentation/examples; they are not indicators of a real attacker.
- A successful login after failures is suspicious enough to review, but it may also be a legitimate user correcting a password.
- An outbound byte count alone does not establish data exfiltration. Validate destination reputation, process/endpoint telemetry, transfer baseline, business purpose, and any relevant DLP or proxy records.
- Record the time range, search, result count, and limitations when saving evidence.
