# STRhub Demo Data

Lightweight public dataset for **[STRhub](https://strhub.app)**, the open-access platform for forensic STR genetics: STR-focused BAM slices from five samples of the *1000 Genomes Project*, BED files with STR coordinates and short reference FASTA slices, for testing and educational use.

## Overview

The BAMs power the embedded [IGV viewer](https://strhub.app/tools/igv-viewer), which opens the hg38 window of each marker with these samples loaded. The FASTA slices power the [FASTA generator](https://strhub.app/tools/fasta-generator). Marker coordinates and structures are described in the [STR marker catalog](https://strhub.app/catalog).

- **Samples:** five public reference samples from the 1000 Genomes Project (HG00097, HG00145, HG00263, HG00372, HG01063)
- **Reference:** GRCh38/hg38
- **Data type:** STR-focused BAM slices (no personal or clinical data)

## Files

| Path | Content |
|---|---|
| `data/<sample>_sort.bam`, `.bai` | Alignments of each sample limited to STR loci, with their index. The IGV viewer streams the same samples from the [0.1 release](https://github.com/Tfronta/strhub-demo-data/releases/tag/0.1) (`<sample>_primary.bam`). |
| `data/regions.bed` | STR coordinates used for slicing (HipSTR-style BED: chromosome, start, end, motif length, repeat count, name). |
| `data/isfg_ranges_grch38.bed` | ISFG minimum ranges in GRCh38 for 22 autosomal STRs (the 20 CODIS core loci plus Penta D and Penta E), in HipSTR's BED format (0-based start), ready for `HipSTR --regions`. |
| `data/isfg_ranges_grch38.tsv` | The same 22 ranges as a table (1-based, inclusive): locus, chromosome, start, end, length in bp, `ce_ref` (the CE allele designation of the GRCh38 reference over that range) and the repeat structure in STRNaming format. |
| `slices/<marker>__slice.fa` | Short GRCh38 sequence around each marker, used by the FASTA generator. |

### ISFG minimum ranges

The ISFG minimum range is the stretch of each STR that forensic sequence nomenclature is reported over. Using it as the genotyping region keeps the reported length in line with the forensic (CE) allele designation: with `ce_ref`, a length difference from the reference (for example HipSTR's `GB` field) is expressed as an allele number as `ce_ref + difference / motif length`.

The ranges come from the STRidER Forensic STR Sequence Guide (FSSG v6-1, sheet *Common Locus Information*, column *ISFG Minimum Range GRCh38 Coordinates*), the material associated with Recommendation 3 of Gettings et al. (2024), *Forensic Science International: Genetics* 68:102946, https://doi.org/10.1016/j.fsigen.2023.102946.

## Disclaimer

> This dataset contains only **publicly available, non-identifiable** genomic regions from the *1000 Genomes Project*.  
> It is provided exclusively for **educational, research, and software testing purposes**.  
> No sensitive or personal genomic data are stored, processed, or shared.  
> STRhub and its maintainers assume no responsibility for third-party use of these files.

## IGV.js Attribution

IGV.js © Broad Institute, distributed under the [BSD-3 License](https://github.com/igvteam/igv.js/blob/master/LICENSE.txt).

Learn more about IGV.js: [https://igv.org/app](https://igv.org/app)

## Citation

If you use these demo datasets, please cite:
> *The 1000 Genomes Project Consortium (2015). A global reference for human genetic variation. Nature, 526, 68–74.*

For the ISFG minimum ranges, cite Gettings et al. (2024), *Forensic Science International: Genetics* 68:102946.

## Contact

Created and maintained by **Tamara Frontanilla**  
For inquiries: [https://strhub.app/about](https://strhub.app/about)
