# EthnoAnatolia Cross-Ref

> **EthnoHack 2026 — Track 1: Traditional knowledge — NLP & AI on historical and ethnobotanical texts**
> Team: botanists · Members: [name 1], [name 2], ...

> ⚠️ **Disclaimer:** This project works with *historical and traditional claims* about plants.
> Extracted passages describe what historical or traditional sources say. They do **not** establish
> efficacy or safety and are **not medical advice**. Do not prepare or ingest any remedy based on this tool.

---

## 1. Project Description

### The chosen challenge
Track 1 — Traditional knowledge: NLP & AI on historical and ethnobotanical texts.

### The problem being solved
In ethnobotanical studies, the literature is scattered and not standardised, so researchers lose a
significant amount of time searching through every source one by one. Cross-referencing the data in
TEMDB with *De materia medica* by Dioscorides — a foundational work of pharmacy and botany — gives a
comprehensive picture of how the use of medicinal plants in Anatolia has evolved from antiquity to the
present and how it has maintained continuity. This is of great importance to us as pharmacists.

### Our solution
A standardised, common dataset that accelerates research, reduces fragmentation in the literature and
allows ancient and modern data to be compared from a single source.

- **Extraction from *De materia medica*:** preparation methods and medicinal uses of Anatolian plants were
  extracted from Dioscorides' *De materia medica* (46 species, 606 use records). Uses were taken from the
  public-domain Sprengel 1829 Latin edition [1] and checked against the Wellmann Greek edition [2]
  (vol. 2; used for verification only, not redistributed).
- **Species selection:** only species recorded **both** in *De materia medica* and in TEMDB were included.
- **ICD-11 coding:** each Dioscorides use was assigned an ICD-11 MMS code using the WHO ICD-11 MMS
  reference document, following the same coding conventions as TEMDB so that the two datasets are
  comparable. *(The ICD-11 coding of TEMDB itself is pre-existing — see Section 2. The coding of the
  Dioscorides uses is new work.)*
- **Cross-referencing with TEMDB:** each historical use was matched to TEMDB records for the same species
  (plant part, preparation and ICD-11 category).
- **Continuity analysis:** for each species and disease category we assessed whether a use described in
  antiquity persists in present-day Anatolian folk medicine, i.e. continuity from antiquity to today.

## 2. Pre-existing work (disclosure)

**TEMDB — Turkish Ethnomedicinal Database** (the dataset we published as a team) · Published 27 August 2026 ·
DOI: [10.5281/zenodo.20002971](https://doi.org/10.5281/zenodo.20002971) · Licence: Creative Commons
Attribution 4.0 International (CC BY 4.0).

TEMDB was used only as a reference and remained unchanged throughout the event. The TEMDB ICD-11
harmonisation and indication coding were completed before the event and were used only as input.

Full details: [`docs/DISCLOSURE.md`](docs/DISCLOSURE.md). Everything else in this repository was created
during the hackathon (2–8 November 2026); see the commit history.

## 3. Technologies

| Category | Used |
|---|---|
| Programming languages | [e.g. Python 3 (Google Colab)] |
| Data sources | Dioscorides, *De materia medica* (Sprengel 1829; Wellmann 1906), TEMDB ([Zenodo](https://doi.org/10.5281/zenodo.20002971)) — see [`data/SOURCES.md`](data/SOURCES.md) |
| Text access | Internet Archive digitised editions and OCR text |
| Disease classification | WHO ICD-11 MMS (reference document) |
| Data processing & analysis | Microsoft Excel |
| AI assistance | Claude (Anthropic) for OCR text reading, data structuring and drafting; all extractions and ICD-11 codes were checked by the team |

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

### Scope and limitations
- Only species recorded **both** in Dioscorides' *De materia medica* and in TEMDB are included (46 species).
- TEMDB currently covers a three-year period of Turkish ethnobotanical literature (2018–2020). A use that is
  absent from TEMDB is therefore **not** evidence that it has disappeared from Anatolian folk medicine;
  it may simply be outside the current coverage.
- TEMDB is being extended by our team as ongoing academic work outside this hackathon; the continuity
  analysis can be re-run as new TEMDB versions are released.

## 9. Repository structure

```
├── data/          # small input files + SOURCES.md (large files: external links)
├── docs/          # DISCLOSURE.md, screenshots
├── outputs/       # generated results
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

## References

1. Dioscorides, P. (1829). *Pedanii Dioscoridis Anazarbei De materia medica libri quinque* (C. Sprengel, Ed.; Vol. 1). Leipzig: C. Cnobloch. (Medicorum Graecorum Opera quae exstant, Vol. 25, C. G. Kühn, Series Ed.). Public Domain. https://archive.org/details/b33286978_0001
2. Dioscorides, P. (1906). *Pedanii Dioscuridis Anazarbei De materia medica libri quinque* (M. Wellmann, Ed.; Vol. 2, Books III–IV). Berlin: Weidmann. https://archive.org/details/b21459162_0002
3. TEMDB — Turkish Ethnomedicinal Database (2026). Zenodo. https://doi.org/10.5281/zenodo.20002971 (CC BY 4.0)
