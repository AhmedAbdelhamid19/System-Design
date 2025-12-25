# 13 - Conclusion and Interview Tips

## Core Problem Recap

- In distributed systems, expect failures and network issues: you cannot assume all machines see the same data or that the network is reliable.

## Practical Advice

- Partition tolerance is mandatory; during partitions you must pick between consistency and availability.
- When explaining a design choice, justify tradeoffs in business terms (e.g., tolerate 5 seconds of staleness for better availability).

## Quick Interview Pointers

- Don’t give absolute answers — explain tradeoffs and why a given choice fits the product requirements.
- Mention CAP where relevant, and tie it to user impact (stale reads vs downtime).

If you'd like, I can:

- Move these files into a different folder (e.g., `docs/system-design/`) or update titles.
- Create a `README.md` table-of-contents that links to all these files.
- Commit the changes and create a Git branch.
