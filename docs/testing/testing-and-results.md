# Testing and Results

The project report records the following validation results from the GNS3 lab:

| Test | Result |
|---|---|
| HA cluster formation | PASS |
| LDAP authentication | PASS |
| Group-based access | PASS |
| Libya → HQ connectivity | PASS — 0% packet loss |
| Tunisia → HQ connectivity | PASS — 0% packet loss |
| Internet access through HQ | PASS |
| IPsec status | PASS |
| SD-WAN SLA | PASS |
| WAN degradation detection | PASS |

## WAN Degradation Scenario

An extended ping test showed normal latency around 5–50 ms, followed by a spike to approximately 620 ms and two timeouts. This demonstrated that the lab could observe degraded WAN conditions through its monitoring setup.

## Challenges Encountered

The implementation included troubleshooting around:

- HA synchronization mismatches
- LDAP bind/authentication failures
- Asymmetric routing across VPN spokes
- Transient WAN latency

These issues were resolved sufficiently for the final validation tests documented in the report.
