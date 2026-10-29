# Log4Shell (CVE-2021-44228) — Security Notes

**CVE:** CVE-2021-44228 — "Log4Shell": JNDI lookup features in Apache Log4j2 do not protect against attacker-controlled LDAP/JNDI endpoints, allowing remote code execution when log messages are controlled by an attacker.

## Severity

- **CVE-2021-44228 CVSS v3.1 score: 10.0 — CRITICAL** (`CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H`)
- Follow-up chained vulnerability: CVE-2021-45046 (Thread Context Lookup) — CVSS v3.1 9.0 CRITICAL

## Affected versions (log4j-core)

- Affected: **`log4j-core` versions `[2.0-beta9, 2.3.1) ∪ [2.4, 2.12.2) ∪ [2.13.0, 2.15.0)`** — i.e. all releases from **2.0-beta9 through 2.15.0**, excluding 2.3.1 and 2.12.2.
- Not affected: **`log4j-api`** JAR alone (no classpath), and **Java** (Log4j itself).

## Fixed versions

| Java version | Minimum safe version (final fix) | Interim milestone that fixed interim CVEs |
|---|---|---|
| Java 8+ | **2.17.1** | 2.15.0 → partial fix; 2.16.0 (fixes CVE-2021-45046); 2.17.0 (fixes CVE-2021-45105); 2.17.1 (fixes CVE-2021-44832) |
| Java 7 | **2.12.4** | 2.12.2 |
| Java 6 | **2.3.2** | 2.3.1 |

> Do not stop at 2.15.0: patching only to 2.15.0 is insufficient (CVE-2021-45046 remains open in non-default configurations; 2.16.0/2.17.0 fix DOs via recursion).

## Sources

- Apache Logging Services — Security page: https://logging.apache.org/log4j/2.x/security.html
- NVD entry for CVE-2021-44228: https://nvd.nist.gov/vuln/detail/cve-2021-44228
- CVE-2021-44228: Log4Shell (Apache Log4j RCE) — Huntress threat library: https://www.huntress.com/threat-library/vulnerabilities/cve-2021-44228
- JPCERT/CC alert (Updated Jan 4, 2022): https://www.jpcert.or.jp/english/at/2021/at210050.html
