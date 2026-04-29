# API Service Unavailable — Incident Runbook
## Overview
This runbook guides on-call engineers through diagnosing and resolving an API service unavailability incident.
## Severity
Depending on the effect gauged, you can gauge the severity level of the situation. 
|Level|Meaning|Example|
|---|---|---|
|**P1-Critical**|All users got affected-Entire service down|API returns 502 for every single request|
|**P2-High**|A lot of users got affected-Partial Outage|API works intermittently — 50% failure rate|
|**P3-Medium**|Either a minor disruption or workaround available|One or a few endpoints are failing, others working fine|
## Symptoms
- Automated monitors do not receive a response from the API within the specified time
- Dashboard flags a high failure rate, say, 4 out of 5 API calls failing
- Customer or support calls reporting API unavailability
## Immediate Actions
1. Acknowledge the alert in your monitoring tool
2. Check the API health endpoint immediately
3. Note the time the incident started
4. Notify your team that you are investigating
## Investigation Steps
Here is a systematic list of steps that you must take to find out the root cause of this situation:
1. Check the health endpoint: `https://api.example.com/health`
2. Check application logs for error patterns
3. Verify API credentials are valid and not expired
4. Check if any deployments happened in the last hour
5. Check if rate limits have been exceeded
6. Test basic network connectivity to the API server
## Escalation
| Scenario | Action | Contact |
|---|---|---|
| Provider-side outage | Check provider status page | Account Manager |
| Credentials expired | Renew API key | Team Lead |
| Deployment issue | Rollback deployment | DevOps Engineer |
| Unknown cause | Escalate immediately | Engineering Manager |
## Resolution
| Cause | Resolution |
|---|---|
| Server overload | Wait for provider to resolve or implement request throttling |
| Network issue | Contact network/infrastructure team |
| Expired credentials | Renew API key and redeploy |
| Bad deployment | Roll back to last stable version |
| Rate limiting | Reduce request frequency or upgrade API plan |
| Provider outage | Monitor provider status page and wait |
## Post-Incident
- Document the incident timeline
- Identify root cause
- Update this runbook if new causes or steps were discovered
- Schedule a post-mortem if P1 or P2 incident