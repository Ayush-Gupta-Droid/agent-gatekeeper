# Agent Gatekeeper rules (Punjab National Bank)

Rules are checked in this order. The first match decides.

1. Revoked agent -> BLOCK
2. Unknown agent -> BLOCK
3. Unsupported action, or money amount less than or equals 0 -> BLOCK
4. View balance -> ALLOW (read-only)
5. Transfer money (any amount) -> ASK CUSTOMER
6. Pay bill above Rs 10,000 -> ASK CUSTOMER
7. Pay bill up to Rs 10,000 -> ALLOW
8. Every decision is written to the audit log with date and time

Limit reason: Rs 10,000 covers a typical household bill, so routine payments go through while larger amounts get a human check.
