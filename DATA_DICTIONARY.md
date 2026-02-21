# Argentina Authority Ledger — Data Dictionary

Canonical files:
- `argentina-authority-ledger-master.jsonl`
- `argentina-authority-ledger-master.jsonl.gz`
- `argentina-authority-ledger-master.csv`
- `argentina-authority-ledger-master.csv.gz`

This is a **multi-modal authority ledger** combining:
- Credentials / provenance (“Great Wall”)
- Web content (Che Argentina Travel complete + Argentina-related TB/NS)
- YouTube transcripts (3 channels, EN + ES/parallel)
- SmugMug photo metadata subset (visual evidence)

## Common fields
- `record_id`, `record_type`, `section`
- `title`, `url` / `canonical_url` (when applicable)
- `provenance` (when available)
- `sha256*` integrity hashes (varies by record type)

## CSV wrapper
`argentina-authority-ledger-master.csv` includes convenience columns plus a `json` column holding the full original JSON record (100% fidelity).
