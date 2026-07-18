# STIX ERW Flare Catalog

This repository provides a catalog of solar flares identified as **Energetically-Rich Weak (ERW) flares**, based on observations from the Spectrometer/Telescope for Imaging X-rays (STIX) onboard the Solar Orbiter mission.

---

## Description

ERW flares are events that show **relatively weak soft X-ray (SXR) emission but strong hard X-ray (HXR) emission**. These events are quantified using the parameter `q_f`, defined as the ratio of HXR fluence to SXR peak flux. This definition is motivated by the integral form of the Neupert effect.

---

## Data Source

The catalog is derived from:

- STIX quicklook observations  
- Energy bands used:
  - **4–10 keV** (SXR)
  - **15–25 keV** (HXR)
- STIX flare lists generated using **STIXDCPY**

Only flares observed when the Solar Orbiter viewing angle is within **±40° of the Sun–Earth line** are included. This avoids backside events and ensures consistency with Earth-based observations.

---

## Method Summary

The ERW flare identification follows a semi-automated approach:

1. SXR peak time and background are obtained from the STIX flare list  
2. HXR peak time is identified within a **2-minute window before the SXR peak**  
3. A proxy for HXR fluence is calculated over the interval leading to the HXR peak  
4. The parameter `q_f` is computed:

   q_f = HXR fluence / SXR peak flux

Flares with high `q_f` values are classified as ERW flares.

---

## Data Columns

Each row in the catalog contains:

- **No.** — Sequence number  
- **SXR Peak time (UT)** — Peak time in 4–10 keV  
- **HXR Peak Time (UT)** — Peak time in 15–25 keV  
- **SXR Peak Counts** — Peak counts in SXR band  
- **HXR Peak Counts** — Peak counts in HXR band  
- **q_f** — Ratio of HXR fluence to SXR peak flux  

---

## Time Coverage

The current dataset includes flares observed during:

- **01 Nov 2023 – 25 Mar 2024**  
- **25 Oct 2024 – 25 Mar 2025**

---

## Notes

- The dataset is based on **quicklook data**, suitable for statistical analysis  
- HXR fluence is a **proxy**, not a full spectral integration  
- The catalog is intended for **statistical and exploratory studies**

---

## References

- Awasthi et al. (2024) — ERW flare identification method  
- Krucker et al. (2020) — STIX instrument  
- Müller et al. (2020) — Solar Orbiter mission  
- Aschwanden (2005) — Neupert effect  

---

## Future Updates

Planned improvements include:

- Extended time coverage  
- Refined ERW selection criteria  
- Additional flare parameters  

---

## Usage

If you use this dataset in your work, please cite the references above and acknowledge this repository.

---

## Contact

For questions or suggestions, please open an issue in this repository.
