# STRhub Demo Data

Lightweight public dataset for **STRhub**, containing preloaded Short Tandem Repeat (STR) regions from a single sample of the *1000 Genomes Project* for testing and educational visualization in **IGV.js**.

## Overview

This repository provides minimal BAM/BAI slices and BED definitions covering selected STR markers (e.g., CODIS and other forensic loci).  
It is designed for **demo purposes only**, allowing users to explore IGV integration without downloading full genomes.

- **Samples:** public reference sample, 1000 Genomes Project
- **Reference:** GRCh38/hg38
- **Data type:** STR-focused BAM slices (no personal or clinical data)
- **Files:**  
  - `data/sample.bam` – alignments limited to STR loci  
  - `data/sample.bam.bai` – BAM index  
  - `data/regions.bed` – STR coordinates used for slicing

## Disclaimer

> This dataset contains only **publicly available, non-identifiable** genomic regions from the *1000 Genomes Project*.  
> It is provided exclusively for **educational, research, and software testing purposes**.  
> No sensitive or personal genomic data are stored, processed, or shared.  
> STRhub and its maintainers assume no responsibility for third-party use of these files.

## IGV.js Attribution

IGV.js © Broad Institute, distributed under the [BSD-3 License](https://github.com/igvteam/igv.js/blob/master/LICENSE.txt).  
A copy of the license is available in `/license/LICENSE_IGV.txt`.

Learn more about IGV.js: [https://igv.org/app](https://igv.org/app)

## Citation

If you use these demo datasets, please cite:
> *The 1000 Genomes Project Consortium (2015). A global reference for human genetic variation. Nature, 526, 68–74.*

## Contact

Created and maintained by **Tamara Frontanilla**  
For inquiries: [https://strhub.org](https://strhub.org) (upcoming)
