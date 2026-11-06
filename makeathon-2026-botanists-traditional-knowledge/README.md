# EthnoAnatolia Cross-Ref

> **EthnoHack 2026 — Track 1: Traditional knowledge — NLP & AI on historical and ethnobotanical texts**
> Team: botanists · Members: [name 1], [name 2], ...

> ⚠️ **Disclaimer:** This project works with *historical and traditional claims* about plants.
> Extracted passages describe what historical or traditional sources say. They do **not** establish
> efficacy or safety and are **not medical advice**. Do not prepare or ingest any remedy based on this tool.

---

## 1. Project Description

### The chosen challenge
[Track 1 — which specific challenge/topic within the track]

### The problem being solved
[2–4 sentences: what problem, for whom, why it matters]

### Our solution
[2–4 sentences: what the tool does, in plain language]

## 2. Pre-existing work (disclosure)

In line with the hackathon originality rule, pre-existing materials used as **frozen inputs** are listed
in [`docs/DISCLOSURE.md`](docs/DISCLOSURE.md). Everything else in this repository was created during the
hackathon (2–8 November 2026); see the commit history.

## 3. Technologies

| Category | Used |
|---|---|
| Programming languages | [e.g. Python 3.11] |
| Libraries & frameworks | [e.g. pandas, requests, rapidfuzz, streamlit] |
| External services / APIs | [e.g. WFO API (hackathon-hosted), WCVP API, ICD-11 API] |
| Data sources | See [`data/SOURCES.md`](data/SOURCES.md) |

## 4. Installation

```bash
git clone https://github.com/[user]/makeathon-2026-botanists-traditional-knowledge.git
cd makeathon-2026-botanists-traditional-knowledge
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS / Linux:
source .venv/bin/activate
pip install -r requirements.txt
```

## 5. How to run

```bash
[command to run, e.g. python src/main.py  or  streamlit run src/app.py]
```

[Describe input → output. Example: "Put the input file in `data/input/`; results are written to `outputs/`."]

## 6. API key management

This repository contains **no API keys**. Keys are read from a local `.env` file that is excluded by `.gitignore`.

1. Copy the template: `cp .env.example .env` (Windows: `copy .env.example .env`)
2. Get the keys you need:

| Service | Where to create the key | Variable in `.env` |
|---|---|---|
| WHO ICD-11 API | Register at https://icd.who.int/icdapi → "View API access key(s)" | `ICD_CLIENT_ID`, `ICD_CLIENT_SECRET` |
| [LLM provider, if used] | [provider console URL] | `LLM_API_KEY` |
| [other] | [...] | [...] |

3. Paste the values into `.env`. The application loads them at start-up (e.g. with `python-dotenv`).

The hackathon-hosted APIs (`*.ethcstwin.di.uoa.gr:65000`) need no key.

## 7. Presentation

- Demo video: [link]
- Screenshots: see [`docs/screenshots/`](docs/screenshots/)
- Slides: [link]

## 8. Data, rights and responsible use

- Every source is listed with its licence, URL and retrieval date in [`data/SOURCES.md`](data/SOURCES.md).
- Only public-domain or openly licensed texts are redistributed. Texts with unclear rights are cited, not copied.
- Historical names may map to zero, one or several modern taxa; the tool records the evidence for each candidate.

## 9. Repository structure

```
├── data/          # small input files + SOURCES.md (large files: external links)
├── docs/          # DISCLOSURE.md, screenshots
├── outputs/       # generated results (git-ignored except samples)
├── src/           # source code
├── .env.example   # template for API keys (copy to .env)
├── .gitignore
├── requirements.txt
└── README.md
```

## 10. Team

| Name | Role | GitHub |
|---|---|---|
| [name] | [role] | [@handle] |

## 11. License

[e.g. MIT for code; data licences as listed in data/SOURCES.md]
