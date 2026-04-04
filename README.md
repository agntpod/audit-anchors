# AGNTPOD Audit Anchors

Tamper-evident audit hash anchoring for the AGNTPOD platform.

Daily SHA-256 hash of the audit chain tip is committed here by an automated process on VPS1. Anchor files contain **only cryptographic hashes** -- no PII.

## Structure

```
anchors/
  2026-04-04.md
  2026-04-05.md
  ...
```

Each file contains:
- Date
- Anchor hash: SHA-256(latest_entry_hash + ':' + row_count + ':' + date)
- Latest entry hash from the audit log
- Row count
- Verification commands

## Verification

Anyone can verify an anchor by running the commands in each anchor file against the VPS1 audit database (with appropriate access).

## Decision

Created per Founder Decision D5 (2026-04-02). Public visibility strengthens tamper evidence.
