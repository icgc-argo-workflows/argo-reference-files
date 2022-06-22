# ICGC-ARGO Reference files
- [Introduction](#introduction)
- [ICGC-ARGO DNA-Seq Analysis](#icgc-argo-dna-seq-analysis)
  - [Reference genome](#reference-genome)
  - [DNA-Seq Alignment](#dna-seq-alignment)
    - [BWA index and auxilary files](#bwa-index-and-auxilary-files)
  - [Sanger Somatic Variant Calling](#sanger-somatic-variant-calling)
    - [Reference genome and annotation files used by Sanger caller](#reference-genome-and-annotation-files-used-by-sanger-caller)
  - [GATK Mutect2 Somatic Variant Calling](#gatk-mutect2-somatic-variant-calling)
    - [Reference files used by GATK Mutect2 caller](#reference-files-used-by-gatk-mutect2-caller)
    - [Additional files needed for scatter and gather](#additional-files-needed-for-scatter-and-gather)
  - [Open Access Variant Filtering](#open-access-variant-filtering)
    - [Genomic regions defined in BED format](#genomic-regions-defined-in-bed-format)
- [ICGC-ARGO RNA-Seq Analysis](#icgc-argo-rna-seq-analysis)
  - [RNA-Seq reference genome](#rna-seq-reference-genome)
  - [RNA-Seq genome annotation files](#rna-seq-genome-annotation-files)
  - [RNA-Seq Alignment](#rna-seq-alignment)
    - [STAR index and auxilary files](#star-index-and-auxilary-files)
    - [HiSAT2 index and auxilary files](#hisat2-index-and-auxilary-files)
    - [Picard-CollectRnaSeqMetrics auxilary files](#picard-collectrnaseqmetrics-auxilary-files)

## Introduction

Reference files used by AROG workflows are hosted at [Cancer Genome Collaboratory](https://cancercollaboratory.org/). File size and MD5 checksums are provided for verifying file integrity after download. Additional files are also included to allow for reproduction of ARGO pipeline analyses. Please see the individual sections for the reference files and how to download and stage them before running the workflows.

## ICGC-ARGO DNA-Seq Analysis

### Reference genome 
- GRCh38 Genome Build Version: [GRCh38DH](http://ftp.1000genomes.ebi.ac.uk/vol1/ftp/technical/reference/GRCh38_reference_genome/)

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| GRCh38_hla_decoy_ebv.fa        | 3263683042 | 64b32de2fc934679c16e83a2bc072064 |
| GRCh38_hla_decoy_ebv.fa.fai    | 154196     | 5ccc91e56dc4a05448dd5b9507ec6bc6 |
| GRCh38_hla_decoy_ebv.fa.gz     | 918931038  | 9513ce08c458ac88f8411dcf01097a1f |
| GRCh38_hla_decoy_ebv.fa.gz.fai | 154196     | 5ccc91e56dc4a05448dd5b9507ec6bc6 |

The above files need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/reference-genome/GRCh38_hla_decoy_ebv/GRCh38_hla_decoy_ebv.fa.fai
```

- This reference genome is used by the ICGC ARGO for DNA-Seq Analysis. This file is composed of the following sequences:
  - GRCh38 primary assembly
  - Decoy sequences
  - Epstein-Barr virus (EBV) sequence
  - Alternate loci scaffolds
  - HLA sequences


### DNA-Seq Alignment

#### BWA index and auxilary files

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| GRCh38_hla_decoy_ebv.dict      | 480732     | eea9d8e1d3a172362f4d16de7415bd79 |
| GRCh38_hla_decoy_ebv.fa.dict   | 480732     | eea9d8e1d3a172362f4d16de7415bd79 |
| GRCh38_hla_decoy_ebv.fa.fai    | 154196     | 5ccc91e56dc4a05448dd5b9507ec6bc6 |
| GRCh38_hla_decoy_ebv.fa.gz.alt | 487553     | b07e65aa4425bc365141756f5c98328c |
| GRCh38_hla_decoy_ebv.fa.gz.amb | 20199      | e4dc4fdb7358198e0847106599520aa9 |
| GRCh38_hla_decoy_ebv.fa.gz.ann | 448319     | f228aeed2106bc6b0cf880317132ac2d |
| GRCh38_hla_decoy_ebv.fa.gz.bwt | 3217347004 | 7f0c8dcfc86b7c2ce3e3a54118d68fbd |
| GRCh38_hla_decoy_ebv.fa.gz.fai | 154196     | 5ccc91e56dc4a05448dd5b9507ec6bc6 |
| GRCh38_hla_decoy_ebv.fa.gz.gzi | 799928     | 11af7c4adcf5d2e211a4ed03a1a8c73e |
| GRCh38_hla_decoy_ebv.fa.gz.pac | 804336731  | 178862a79b043a2f974ef10e3877ef86 |
| GRCh38_hla_decoy_ebv.fa.gz.sa  | 1608673512 | 91a5d5ed3986db8a74782e5f4519eb5f |

The above files need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/reference-genome/GRCh38_hla_decoy_ebv/GRCh38_hla_decoy_ebv.dict
```

### Sanger Somatic Variant Calling

#### Reference genome and annotation files used by Sanger caller

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| CNV_SV_ref_GRCh38_hla_decoy_ebv_brass6+.tar.gz      | 4257793984 | 90a100d06dbde243c6e7e11e6a764374 |
| SNV_INDEL_ref_GRCh38_hla_decoy_ebv-fragment.tar.gz  | 1550158859 | 03ac504f1a2c0dbe34ac359a0f8ef690 |
| VAGrENT_ref_GRCh38_hla_decoy_ebv_ensembl_91.tar.gz  | 90122115   | 876657ce8d4a6dd69342a9467ef8aa76 |
| core_ref_GRCh38_hla_decoy_ebv.tar.gz                | 899142864  | 6448a15bcc8f91271b1870a3ecfcf630 |
| qcGenotype_GRCh38_hla_decoy_ebv.tar.gz              | 11472540   | 1956e28c1ff99fc877ff61e359e1020c |

The above files were originated from [Sanger Reference Archives](https://github.com/cancerit/dockstore-cgpwgs/wiki/Reference-archives#human-grch38) and need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/sanger-variant-calling/qcGenotype_GRCh38_hla_decoy_ebv.tar.gz
```

### GATK Mutect2 Somatic Variant Calling

#### Reference files used by GATK Mutect2 caller

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| 1000g_pon.hg38.vcf.gz                                  | 17273497   | e236330d8d156d2aad2d0930a2440177 |
| 1000g_pon.hg38.vcf.gz.tbi                              | 1534802    | b95230d6634c3926fb0b4f104518a0f5 |
| af-only-gnomad.hg38.vcf.gz                             | 3184275189 | a4209be7fb4b5a5a8d3b778132cb7401 |
| af-only-gnomad.hg38.vcf.gz.tbi                         | 2443190    | a7efccb1519f046c19cdf9f28559d747 |
| af-only-gnomad.pass-only.biallelic.snp.hg38.vcf.gz     | 3529021364 | 6009ac7799419f69f19957a2ba1b3a16 |
| af-only-gnomad.pass-only.biallelic.snp.hg38.vcf.gz.tbi | 3121555    | 54bbff8e5637e5505eb06a0186d9b306 |
| af-only-gnomad.pass-only.hg38.vcf.gz                   | 4461091562 | 1c0240e5b752c8e414a86d204e4768fb |
| af-only-gnomad.pass-only.hg38.vcf.gz.tbi               | 3259267    | c537795d90d71e56279545e1682f5fdf |
| small_exac_common_3.hg38.vcf.gz                        | 1297183    | 4c75c1755a45c64e8af7784db7fde009 |
| small_exac_common_3.hg38.vcf.gz.tbi                    | 242095     | f650d1dda6bd68cba65d77f131147985 |


The above files were originated from [GATK Best Practices Resources](https://console.cloud.google.com/storage/browser/gatk-best-practices/somatic-hg38) and need to be staged under a path in the file system where workflow jobs can access. The files can be downloaded using `wget`, one example is given as below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/gatk-resources/1000g_pon.hg38.vcf.gz
```
#### Additional files needed for scatter and gather

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| mutect2.scatter_by_chr/chr1.interval_list  | 180 | 24d9137f7ccd5c2803d58ef56b8b3f53 |
| mutect2.scatter_by_chr/chr10.interval_list | 182 | 512975027d78247fcb19166882fd51bf |
| mutect2.scatter_by_chr/chr11.interval_list | 182 | 4e51ed603da33710c7f1b8698f79649d |
| mutect2.scatter_by_chr/chr12.interval_list | 182 | 0f29b41613170edfca43fd27073c5079 |
| mutect2.scatter_by_chr/chr13.interval_list | 182 | d4dd4925e687cc9fce124dee7b063bb2 |
| mutect2.scatter_by_chr/chr14.interval_list | 182 | 17b4b3f0e549ed5acd1d4897bf8d0100 |
| mutect2.scatter_by_chr/chr15.interval_list | 182 | 9cfd133e2e3f90e37f8097048285e927 |
| mutect2.scatter_by_chr/chr16.interval_list | 180 | 9f4b5fb8db1493214d1aa540aecfc231 |
| mutect2.scatter_by_chr/chr17.interval_list | 180 | ff20b86a75cf9f329e2b935ea4edb2d3 |
| mutect2.scatter_by_chr/chr18.interval_list | 180 | 7607a18fa2a9ef98b4548c3d19e905c4 |
| mutect2.scatter_by_chr/chr19.interval_list | 180 | 2d95d0b4dc2282215c1981f759335ff4 |
| mutect2.scatter_by_chr/chr2.interval_list  | 180 | 9991a595530b6b06cafdb4ec62e6b419 |
| mutect2.scatter_by_chr/chr20.interval_list | 180 | 645342a858273248874e99acb29c50d5 |
| mutect2.scatter_by_chr/chr21.interval_list | 180 | 46907e8a00757980748c4a39864b8af5 |
| mutect2.scatter_by_chr/chr22.interval_list | 180 | fe4a33ce8693de2384ab447fb09f6f1b |
| mutect2.scatter_by_chr/chr3.interval_list  | 180 | 0548550722522719b2e4f0a1c8c3de42 |
| mutect2.scatter_by_chr/chr4.interval_list  | 180 | 191cdd70699c18d9fc68af035f00b0ef |
| mutect2.scatter_by_chr/chr5.interval_list  | 180 | f6e3b6b42e3f020c476aa89e7cbb32fc |
| mutect2.scatter_by_chr/chr6.interval_list  | 180 | e639558c71d116419dfcf41bbd2a4413 |
| mutect2.scatter_by_chr/chr7.interval_list  | 180 | b166ff8931a4ef196052b7cf961e71d3 |
| mutect2.scatter_by_chr/chr8.interval_list  | 180 | 86971574be70f3c6a38c8f6f8ad74f26 |
| mutect2.scatter_by_chr/chr9.interval_list  | 180 | b4aa7ed56e505cf6f9b0eca9ddc8c319 |
| mutect2.scatter_by_chr/chrXY.interval_list | 358 | bfef3db07d46c8d8d5c893c3cca827f3 |
| bqsr.sequence_grouping.grch38_hla_decoy_ebv.csv               | 89497 | 8ea70d26ffae94f8e14f321a7c0e7680 |
| bqsr.sequence_grouping_with_unmapped.grch38_hla_decoy_ebv.csv | 89509 | 1f6db058b2209485852059ecb69d7535 |

These files have been checked into [GitHub repository](https://github.com/icgc-argo/gatk-mutect2-variant-calling/tree/main/assets)
for the Mutect2 workflow. To get the files you may just clone the repo, or download using
`wget` using the URL pattern as in the following example:

```
wget https://raw.githubusercontent.com/icgc-argo/gatk-mutect2-variant-calling/main/assets/mutect2.scatter_by_chr/chr1.interval_list
```

### Open Access Variant Filtering
#### Genomic regions defined in BED format
| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| open_access.gencode_v38.20210915.bed.gz | 129538 | 6c6781661cd3bf2c3060577e597928d3 |

The file has been checked into [GitHub repository](https://github.com/icgc-argo/open-access-regions/tree/main/data/hg38/bed/gencode.v38) for the workflow. To get the file you may just clone the repo, or download using
`wget` using the URL pattern as in the following example:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/open-access-regions/open_access.gencode_v38.20210915.bed.gz
```


## ICGC-ARGO RNA-Seq Analysis
### RNA-Seq reference genome 
- GRCh38 Genome Build Version: [GRCh38_Verily_v1](https://console.cloud.google.com/storage/browser/genomics-public-data/references/GRCh38_Verily)

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| GRCh38_Verily_v1.genome.fa        | 3150152408 | 16626761857940321a7a1142e03f8217 |
| GRCh38_Verily_v1.genome.fa.fai     | 123145  | b373ad1f64003c910dce216f93718aab |
| GRCh38_Verily_v1.genome.fa.gz | 887918831 | 1fb31dcb45ca7c52d0e27c523504bc9a |
| GRCh38_Verily_v1.genome.fa.gz.gzi | 772104 | 55b7a860d1cef3793fcda54af56664e3 |
| GRCh38_Verily_v1.genome.fa.gz.fai | 123145 | b373ad1f64003c910dce216f93718aab |
| README.txt  | 1492  | db3b3e4233b6ddb92ff3e3dc152ccda8 |

The above files need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/rna-seq-references/GRCh38_Verily_v1.genome/README.txt
```


- Since RNA-Seq aligners are not ALT-aware, a slightly different version of reference genome is used by ICGC-ARGO for RNA-Seq Analysis. This file is composed of the following sequences:
  - GRCh38 primary assembly
  - Decoy sequences
  - Epstein-Barr virus (EBV) sequence

### RNA-Seq genome annotation files
- [GENCODE v40](https://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_40/gencode.v40.chr_patch_hapl_scaff.annotation.gtf.gz) contains the comprehensive gene annotation on the reference chromosomes, scaffolds, assembly patches and alternate loci (haplotypes)

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| gencode.v40.chr_patch_hapl_scaff.annotation.gtf        | 1616162883 | beeee37565d2a76f477fb474fcfa922e |

The above files need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/rna-seq-references/GRCh38_Verily_v1.annotation/gencode.v40.chr_patch_hapl_scaff.annotation.gtf
```

### RNA-Seq Alignment
#### STAR index and auxilary files

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
|Genome|3823751360|c40d86d0b50c34dd46a9347472462937|
|SA|24750976325|318f38f408c9b48e8c2e4c4911bcf470|
|SAindex|1565873619|aa883f548dbc9399e7a1444891fdd741|
|STARindex.log|763|acb99118146c8723378709968565c3c4|
|chrLength.txt|13158|7f5964f5965ea24ade6257990c7461cf|
|chrName.txt|66140|fbb1fe18634dc8fc7192930225f0e6a1|
|chrNameLength.txt|79298|98e83030349933a0b0ca21888a71edb0|
|chrStart.txt|28378|d87a026a4ec84d67c3e53256a985f904|
|exonGeTrInfo.tab|56068230|696ce75a16af0d50a47f79c4b95ff4b1|
|exonInfo.tab|22952209|8932772eace6ab5408133590b4f34b56|
|geneInfo.tab|2591817|303aa1d1f63fae8bd954dba3c5f5dcb9|
|genomeParameters.txt|1008|7ad39ed85712bdb3f7e238e364f39de4|
|sjdbInfo.txt|11620218|29b9af281debb5900d8db82f832a0642|
|sjdbList.fromGTF.out.tab|12610890|1d4d6966ec9f67d9125067b7636c3038|
|sjdbList.out.tab|10259582|207834d2baf062f5d0a303c18fdb8798|
|transcriptInfo.tab|16599748|445aa2a51ddfc112f0f6f6b8463f9b8d|


The above files need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/rna-seq-references/GRCh38_Verily_v1.STARindex.sjdbOverhang_75/STARindex.log
```


#### HiSAT2 index and auxilary files

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
|GRCh38_Verily_v1.1.ht2 | 1818403521 |  60998540231f7e21ad8a53d13898de08 |
|GRCh38_Verily_v1.2.ht2 | 736877080 | a6b58d2aa00d32007c1227e9835e2038 |
|GRCh38_Verily_v1.3.ht2 | 31508 | 682418739b6d9c3dd92dc39df73fdfeb |
|GRCh38_Verily_v1.4.ht2 | 735167267 | aac99bf451926a49e0cb5a921588fdf2 |
|GRCh38_Verily_v1.5.ht2 | 1772593003 | 834ad923bead0a77562f80ea55ed3c93 |
|GRCh38_Verily_v1.6.ht2 | 749013982 | 89110c7f502a5ffa5fd9895cba2f87da |
|GRCh38_Verily_v1.7.ht2 | 14465092 | bef9ed20ad08932a0d07b5da317be62b |
|GRCh38_Verily_v1.8.ht2 | 2823782 | 4bfcde812f6b0ce124439d6da85ccdf6 |
|GRCh38_Verily_v1.log | 10620 | 4e833f06e59568c17e409b1a69cf7b11 |

The above files need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/rna-seq-references/GRCh38_Verily_v1.HISAT2index/GRCh38_Verily_v1.log
```

#### Picard-CollectRnaSeqMetrics auxilary files
- `--ref_flat`: a tab-delimited file containing information about the location of RNA transcripts, exon start and stop sites, etc. 
- `--ribosomal_interval_list`: provide the locations of rRNA sequences in the genome in interval_list format. If not specified no bases will be identified as being ribosomal. 

| file name | size | md5sum |
|--------------------------------|------------|----------------------------------|
| GRCh38_Verily_v1.rRNA.interval_list | 4089 | e5f74657a1277d75fa6f4eab495f6370 |
| GRCh38_Verily_v1.refFlat.txt.gz | 8043021 | 21ebee2684e7be6df13500d880b2b6ad |

The above files need to be staged under a path in the file system where workflow
jobs can access. The files can be downloaded using `wget`, one example is given as
below:

```
wget https://object.cancercollaboratory.org:9080/swift/v1/genomics-public-data/rna-seq-references/GRCh38_Verily_v1.Picard_CollectRnaSeqMetrics/GRCh38_Verily_v1.rRNA.interval_list
```


