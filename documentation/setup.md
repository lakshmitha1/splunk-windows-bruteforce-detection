# Setup and Testing

## Environment

- Windows endpoint
- Splunk Universal Forwarder
- Splunk Enterprise
- Splunk Enterprise Security

## Data Flow

Windows Endpoint
→ Universal Forwarder
→ Splunk Enterprise
→ Splunk Enterprise Security

## Windows Security Logs

The project uses Windows Security logs.

Event ID 4625 represents failed Windows logon attempts.

## Detection

The detection searches for multiple failed login attempts from the same host.

The threshold used in this project is 4 failed logins.

## Correlation Search

- Detection window: 10 minutes
- Schedule: Every 5 minutes
- Scheduling: Continuous
- Trigger: Number of Results greater than 0
- Trigger mode: Once
- Throttling: 10 minutes
- Group by: host

## Testing

Four failed Windows login attempts were generated on the Windows endpoint.

The events were successfully received by Splunk as Event ID 4625.

## Troubleshooting

During testing, the correlation search encountered scheduler concurrency limitations on the shared Splunk environment.

Scheduler logs showed that the maximum number of concurrent historical scheduled searches had been reached.

## Result

The Windows Security events and brute-force detection SPL were successfully validated.

The correlation search configuration was created and scheduler behavior was investigated.
