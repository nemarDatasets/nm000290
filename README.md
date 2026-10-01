[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.nm000290-blue)](https://doi.org/10.82901/nemar.nm000290)

# PROTEUS BCI Bordeaux — EEG/EMG Foundation Challenge 2026, Track 02

EEG recorded with a 64-channel actiCAP slim / actiCHamp system (Brain Products); 41 EEG channels are provided,
sampled at 500 Hz, reference M1 (mastoid), ground FpZ, stored as EDF+ (µV, per-file digital scaling).

## Contents
- 10 participants (labels `sub-P##`), 14 sessions, 112 runs.
  Sessions per participant: 1, 3. Session labels are chronological.
- Each session contains up to 8 runs:
  - `BaselineOE` / `BaselineCE` (run 0): rest, eyes open / eyes closed.
  - `AcquisitionGraz`, `AcquisitionBH`: calibration runs with sham feedback (Graz and BrainHero interfaces).
  - `OnlineRawGraz`, `OnlineRawBH` (two runs each): online runs with real feedback.
- Three cued mental tasks: `mi` (kinesthetic motor imagery of the non-dominant hand), `sub` (mental subtraction),
  `word` (word generation from a given letter). Cue onsets are the `mi` / `sub` / `word` rows of `*_events.tsv`
  (OpenViBE codes 33024 / 33025 / 33026, also stored as EDF+ annotations).
- `participants.tsv`: age (binned). `sub-*_sessions.tsv`: session labels only (questionnaires withheld).

## Known issues
- `BAD_ACQ_SKIP` marks the padding (< 1 s) at the end of the last 1-s EDF record of each run; it is not a gap.
- 1 runs have an EDF resolution coarser than 1 µV per bit (per-file digital scaling).
- 13 cued runs have fewer trials than is usual for their run type.

## Licence
Creative Commons Attribution 4.0 International (CC-BY-4.0). Authors: Dreyer Pauline, Bourdil Manon, Bechon Loic, Kojima Simon, Velut Sebastien, Rimbert Sebastien, Roy Raphaëlle, Lotte Fabien.
