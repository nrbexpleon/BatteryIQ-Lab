# Threat model

| Threat | Current control | Production work |
|---|---|---|
| Malformed/oversized telemetry | strict types, ordering and hard bounds | schema registry, streaming validation and fuzzing |
| Spoofed pack identity | explicit identity fields | authenticated vehicle identity and certificates |
| Sensor/data manipulation | explainable checks and evidence hash | signed telemetry, secure gateway, plausibility fusion |
| Evidence tampering | SHA-256 and optional RSA signature | HSM/KMS, secure timestamp, immutable repository |
| Unauthorized API access | loopback default and optional token | OIDC, roles, tenant isolation and audit |
| Sensitive vehicle data leakage | synthetic public fixtures | encryption, retention, redaction and data governance |
| Unsafe control | no write/actuator API | independently assessed BMS safety gateway |
| Resource exhaustion | request/sample/cell/run bounds | rate limits and isolated workers |

Never commit production VINs, pack serials, credentials, keys or client telemetry.
