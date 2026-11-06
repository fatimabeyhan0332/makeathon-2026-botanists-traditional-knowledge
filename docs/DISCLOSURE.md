# Disclosure of pre-existing work

The EthnoHack 2026 rules require that work is created or substantially developed during the hackathon
(2–8 November 2026) and that any pre-existing parts are clearly disclosed. This file lists them.

## Pre-existing inputs (created before the event, used unchanged)

| Item | Description | Origin / date | How it is used here |
|---|---|---|---|
| TEMDB — Turkish Ethnomedicinal Database | Dataset published by our team before the hackathon | Published 27 August 2026 · DOI: [10.5281/zenodo.20002971](https://doi.org/10.5281/zenodo.20002971) · Licence: CC BY 4.0 | Used only as a frozen reference/input; it was **not modified** during the event |
| TEMDB ICD-11 harmonisation and indication coding | ICD-11 coding of TEMDB indications | Completed by our team **before** the event (October 2026) | Used only as input; **not presented as hackathon work** |

## Created during the hackathon (2–8 November 2026)

- **Extraction from *De materia medica*:** preparation methods and medicinal uses of Anatolian plants
  were extracted from Dioscorides' *De materia medica* (46 species, 606 use records). Uses were taken
  from the public-domain Sprengel 1829 Latin edition and checked against the Wellmann Greek edition
  (vol. 2; used for verification only, not redistributed).
  *Species selection:* only species recorded **both** in *De materia medica* and in TEMDB were included.
- **New ICD-11 coding of the historical uses:** every Dioscorides use was assigned an ICD-11 MMS code
  using the WHO ICD-11 MMS reference document, following the same coding conventions as TEMDB so that
  the two datasets are comparable. *(The ICD-11 coding of TEMDB itself is pre-existing; see above.
  The coding of the Dioscorides uses is new work.)*
- **Cross-referencing with TEMDB:** each historical use was matched to TEMDB records for the same
  species (plant part, preparation and ICD-11 category).
- **Continuity analysis:** for each species and disease category we assessed whether a use described
  in antiquity persists in present-day Anatolian folk medicine, i.e. continuity from antiquity to today.
- All code in `src/` and all results in `outputs/`.

The commit history of this repository documents when each part was written.
