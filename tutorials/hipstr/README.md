# Practice data: STRhub HipSTR tutorial

The exact files used in the [STRhub HipSTR tutorial](https://strhub.app/tools/hipstr/tutorial) and its video. With them you can run every step and get the same output the tutorial shows, before trying your own files.

## Download

In the working folder you set up in the tutorial (`hipstr-tutorial`), run:

```bash
for f in NA12878.bam NA12878.bam.bai GRCh38_STR_regions.fa.gz GRCh38_STR_regions.fa.gz.fai \
         GRCh38_STR_regions.fa.gz.gzi regions.bed isfg_ranges_grch38.tsv; do
  curl -fLO https://raw.githubusercontent.com/Tfronta/strhub-demo-data/main/tutorials/hipstr/$f
done
```

About 20 MB. There is no need to clone this repository: it holds much larger files.

## Files

| File | Size | SHA-256 | Content |
|---|---|---|---|
| `NA12878.bam` | 9.8 MB | `f5f73e9f4f4a483794716111a61231e478c0de10113a8d55598ed4b31481e9b7` | Illumina reads of NA12878 (Genome in a Bottle HG001, 300x), aligned to GRCh38, only around 24 forensic STRs (±1,000 bp). Read group `SM:NA12878`. |
| `NA12878.bam.bai` | 0.8 MB | `e657838c2f3d875f37ab5b7099996569b1ade8cab7336b97dddc2052fd704c3d` | Index of the BAM. |
| `GRCh38_STR_regions.fa.gz` | 9.4 MB | `fb36b7c8d638e56593697d768d7b8c5fd6897977ad5f93b550f9582d74a59507` | Reduced GRCh38: every base set to N except 5,000 bp around each STR. With the tutorial's commands, HipSTR writes the same VCF records as with the full GRCh38. |
| `GRCh38_STR_regions.fa.gz.fai` | 568 B | `195031192cda9eb807f2b8b5e255a71b485addad072405741ddb9aede6c6781d` | Index of the reference. |
| `GRCh38_STR_regions.fa.gz.gzi` | 0.6 MB | `36f1eb02b970724aa3cb8986306f75b93616a6c64b397f6fcb9be9dd43a84ffb` | bgzip index of the reference. |
| `regions.bed` | 789 B | `7b6217eb9adb10c0f5fb5829c4249efc283566600e31268887e65a244ac42987` | ISFG minimum ranges of 22 forensic STRs (the 20 CODIS core loci plus Penta D and Penta E), in HipSTR's BED format. Same file as `data/isfg_ranges_grch38.bed`. |
| `isfg_ranges_grch38.tsv` | 1.3 KB | `891ca09b1cbc48505aa443ce19fa8245196f641d06ae4cb939ab6401be0c079b` | The same ranges as a table, with `ce_ref` (the CE allele number of the reference). Same file as `data/isfg_ranges_grch38.tsv`. |

To check a download: `shasum -a 256 NA12878.bam` (macOS) or `sha256sum NA12878.bam` (Linux and WSL).

## Where the data come from

- **Reads:** Genome in a Bottle (GIAB) / NIST, NA12878 (HG001) 300x Illumina WGS, `HG001.GRCh38_full_plus_hs38d1_analysis_set_minus_alts.300x.bam`, from https://ftp-trace.ncbi.nlm.nih.gov/ReferenceSamples/giab/data/NA12878/NIST_NA12878_HG001_HiSeq_300x/. Sliced with `samtools view` around 24 autosomal forensic STRs (±1,000 bp), sorted, given a read group and indexed.
- **Reference:** GRCh38 (UCSC hg38), reduced to 5,000 bp around each STR.
- **ISFG minimum ranges:** STRidER Forensic STR Sequence Guide (FSSG v6-1), Recommendation 3 of Gettings et al. (2024), *Forensic Science International: Genetics* 68:102946, https://doi.org/10.1016/j.fsigen.2023.102946.

Open-access reference data, for education, research and software testing only: not for donor identification or database searching.
