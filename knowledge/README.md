# Scientific knowledge snapshot

Mechanically synchronized every three hours from a PostgreSQL REPEATABLE READ,
READ ONLY transaction. The database connection is closed before Git/network work.
No agent, model inference, source fetch, or knowledge mutation runs in this job.

`manifest.json` records the snapshot time, schema, columns, primary keys, row
counts, and SHA-256/size of each file. `tables/` contains UTF-8 JSON Lines,
deterministically partitioned by primary key. All files in a commit belong to
one database snapshot. Git history retains earlier exports and corrections.

Sources, original URLs, parsed evidence text and exact spans, entities, events,
claims/evidence, provenance, temporal world states, trajectories, questions,
ranking packets/decisions and editorial outcomes are included. Historical and
candidate records are retained: presence does NOT mean admission or scientific
truth. `admission.jsonl` supplies event admission and canonical identity at the
export cutoff; preserve timestamps, status and evidence when consuming records.

Excluded: pending raw ingestion leads, execution queues/logs, model transcripts,
credentials, runtime configuration and raw HTML/PDF binary objects. Content-hash
object references remain identifiers; their binary objects live in the local
evidence backup. Parsed source text is included. This is a portable knowledge
dataset, NOT a complete runtime disaster-recovery backup. Some task IDs refer to
the excluded local execution ledger. Original publishers retain their rights.
