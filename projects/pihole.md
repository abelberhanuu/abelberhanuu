# Homelab: Network-Wide Ad Blocker

A Debian Linux homelab project using Pi-hole to apply DNS filtering across home devices.

## Technical contribution

- Deployed Pi-hole on Debian Linux to filter advertising and tracking domains.
- Monitored DNS queries for unusual traffic and investigated Linux service issues.
- Maintained filtering as an ongoing home-network service, beginning July 2025.

## Outcome and scope

The deployment provides shared DNS filtering for devices configured to use it, rather than requiring a separate browser extension on each device.

**Scenario estimate:** approximately 500,000 blocked DNS queries, calculated as an assumed 1,000 daily blocks multiplied by roughly 500 days. This is an assumption-based estimate, not a measured counter or a count of individual ads. Device count, measured block rate, and uptime are not reported here.

## Retrieve a measured result

On the Pi-hole host, where SQLite is installed and the database uses its default path:

```bash
sudo sqlite3 -readonly /etc/pihole/pihole-FTL.db \
  "SELECT value AS blocked_queries FROM counters WHERE id = 1;"
```

This counter covers the lifetime of the current database table. Recreating or resetting the database can change the period represented. Keep household browsing histories and client identifiers private when sharing results.

Reference: [Pi-hole query database and counters](https://docs.pi-hole.net/database/query-database/).

## Portfolio evidence

This page documents the deployment described in my resume. A reproducible configuration export, redacted dashboard image, and measured counter would provide additional evidence of its scope.
