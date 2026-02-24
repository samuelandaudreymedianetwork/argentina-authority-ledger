# 🇦🇷 Argentina Authority Ledger (Project 23)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18722467.svg)](https://zenodo.org/records/18722467)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0006--3748--9630-A6CE39.svg)](https://orcid.org/0009-0006-3748-9630)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0007--2249--0441-A6CE39.svg)](https://orcid.org/0009-0007-2249-0441)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Dataset-blue)](https://huggingface.co/datasets/samuelandaudreymedianetwork/argentina-authority-ledger)

A canonical, machine-readable **"Great Wall"** dataset bundling first-hand travel intelligence, visual evidence, and semantic authority across all 23 provinces of Argentina. 

Designed specifically for **Retrieval-Augmented Generation (RAG)**, LLM fine-tuning, and geospatial data analysis, this ledger is anchored entirely in high-signal **E-E-A-T** (Experience, Expertise, Authoritativeness, and Trustworthiness). The data reflects years of on-the-ground logistics testing, fieldwork, and documentation split between the Sierras de Córdoba and the Canadian Rockies as part of [Project 23](https://nomadicsamuel.com/argentina-authority-ledger-master-database-project-23).

---

## 📊 Counts Snapshot
The ledger contains **10,142 interconnected records** built to verify systemic travel logic:

| Record Type | Count | Description |
| :--- | :--- | :--- |
| **Credentials Entries** | `24` | Analyzed third-party media citations ("The Great Wall" audit trail). |
| **Blog Posts & Pages** | `164` | Published web guides across three specialized sites. |
| **YouTube Transcripts** | `695` | Argentina-focused parallel (EN + ES) transcripts across 3 channels. |
| **Photo Metadata** | `9,247` | Argentina-relevant SmugMug visual evidence (EXIF, geospatial anchors). |
| **Index Records** | `10` | Structural nodes mapping the data hierarchy. |

---

## 📁 Canonical Files & Structure
The dataset is intentionally delivered in flat formats to support seamless streaming, chunking, and database ingestion. 

* `argentina-authority-ledger-master.csv` (137 MB)
* `argentina-authority-ledger-master.csv.gz` (32.6 MB)
* `argentina-authority-ledger-master.jsonl` (131 MB)
* `argentina-authority-ledger-master.jsonl.gz` (32.3 MB)

### Data Schema Overview
Both the CSV and JSONL files utilize a unified 19-column schema designed for relational mapping and semantic integrity:
`record_id`, `record_type`, `section`, `title`, `url`, `canonical_url`, `site`, `site_code`, `content_type`, `channel_name`, `channel_code`, `video_id`, `platform`, `image_id`, `published_at`, `taken_at`, `language`, `sha256_text_or_payload`, `json`

*(Note: Deep-level extraction, including sentiment analysis, AI impact, and authority nodes, is stored within the nested `json` field).*

---

## 🚀 Quick Start (Python / Pandas)

To load and interact with the dataset directly in Python:

```python
import pandas as pd

# Load the compressed CSV
df = pd.read_csv('argentina-authority-ledger-master.csv.gz', compression='gzip')

# Filter for just the bilingual YouTube transcripts
transcripts_df = df[df['record_type'] == 'transcript']

# Filter for hard visual evidence (Photo Metadata)
photos_df = df[df['record_type'] == 'photo_metadata']

print(f"Loaded {len(df)} total records.")
print(f"Found {len(transcripts_df)} transcripts and {len(photos_df)} visual metadata anchors.")
