## Title
### Contents
* [Overview](#Overview)
* [System Requirements](#System-Requirements)
* [Installation Guide](#Installation-Guide)
* [Running and outputs](#Running-and-outputs)
* [Issues](#Issues)
### Overview
CRC_code is a package containing tools for comprehensive analysis of cf-mtDNA fragmentomic features, that is capable of dealing with sequencing data. The code also  can be employed to calculate the probability of developing gastric cancer, thereby enhancing the capabilities for early detection of gastric cancer.
### System Requirements
*Hardware Requirements*

Code in this web site requires only a standard computer with enough RAM to support the operations defined by a user. For minimal performance, this will be a computer with about 2 GB of RAM. For optimal performance, we recommend a computer with the following specs:

RAM: 16+ GB CPU: 4+ cores, 3.3+ GHz/core

*Software Requirements*

OS Requirements

This package is supported for MacOS,Windos and Linux systems.The package development version is tested on Linux operating systems on CentOS 7.9.
The CRAN package should be compatible with Windows, Mac, and Linux operating systems.
Before setting up the package, users should have R version 3.4.0 or higher , randomForest and several packages set up from CRAN should installed.Python scripts is tested on 3.10.9 and python3 is recommended. To avoid some conflicts between softwares, anaconda or miniconda package manager and virtual environment are also recommended.

*Packages and Softs Dependencies*

The code mainly depends on the Python scientific stack.

```
numpy==1.23.5
pandas==1.5.3
scipy==1.10.0
pysam==0.22.0
samtools==1.15.1
picard-tools==1.81
```

### Installation Guide
Install anaconda 2.Create and activate virtul envirment

```
conda create -n your_env_name python=3.10.9  
source activate your_env_name  
pip install pandas==1.5.3 scipy==1.10.0 pysam==0.22.0  
conda install samtools  
conda install r-base=4.3.0  
#R language mode insatll model package  
install.packages ("randomForest")
```

### Running and outputs
*Running*  
We have put the cfDNA fragment compute scripts together in a shell script named run_fragment_study.sh.Opening a terminal and run the scprit as follow:
```
bash run_fragment_study.sh
```
*Outputs*  
The output of run_fragment_study.sh as follow:
```
fragment_study
├── fragment_study/insertszie
│   ├── fragment_study/insertszie/cumsumfrequency
│   │   ├── fragment_study/insertszie/cumsumfrequency/mis10_insertsize_cufrequency.csv
│   │   ├── fragment_study/insertszie/cumsumfrequency/mis10_insertsize_cumfrequency50%_insertsize.csv
│   │   └── fragment_study/insertszie/cumsumfrequency/mis10_insertsize_excluded_sample.csv
│   └── fragment_study/insertszie/mis_10_insertsize_mtr.csv
├── fragment_study/mis_10_endmotifs_4base
│   ├── fragment_study/mis_10_endmotifs_4base/endmotifs_total_ratio.csv
│   ├── fragment_study/mis_10_endmotifs_4base/endmotifs_total.csv
│   └── fragment_study/mis_10_endmotifs_4base/MDS
│       └── fragment_study/mis_10_endmotifs_4base/MDS/four_bases_enmotifs_entropy.csv
└── fragment_study/mis_10_splitedBy125
    ├── fragment_study/mis_10_splitedBy125/125_splited_sam_file
    │   ├── fragment_study/mis_10_splitedBy125/125_splited_sam_file/GC-116cf.mis.10.L125.sam
    │   ├── fragment_study/mis_10_splitedBy125/125_splited_sam_file/GC-116cf.mis.10.S125.sam
    │   ├── fragment_study/mis_10_splitedBy125/125_splited_sam_file/GC-120cf.mis.10.L125.sam
    │   └── fragment_study/mis_10_splitedBy125/125_splited_sam_file/GC-120cf.mis.10.S125.sam
    ├── fragment_study/mis_10_splitedBy125/depth_file
    │   ├── fragment_study/mis_10_splitedBy125/depth_file/GC-116cf.mis.10.L125.sam.txt
    │   ├── fragment_study/mis_10_splitedBy125/depth_file/GC-116cf.mis.10.S125.sam.txt
    │   ├── fragment_study/mis_10_splitedBy125/depth_file/GC-120cf.mis.10.L125.sam.txt
    │   └── fragment_study/mis_10_splitedBy125/depth_file/GC-120cf.mis.10.S125.sam.txt
    ├── fragment_study/mis_10_splitedBy125/depth_stat_LS125_cunt.csv
    ├── fragment_study/mis_10_splitedBy125/depth_stat_LS125_ratio.csv
    ├── fragment_study/mis_10_splitedBy125/depth_stat_LS125_zfsd.csv
    └── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline
        ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/AUDC
        │   ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/AUDC/255_audc_nega.csv
        │   └── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/AUDC/255_audc_posi.csv
        ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/corr
        │   └── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/corr/after_smothed_corr_with_mean_of_baseline.csv
        ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/ED
        │   ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/ED/euclidean_of_zfsd_and_HC_median.csv
        │   ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/ED/euclidean_of_zfsd_and_HC_median_in_255.csv
        │   └── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/ED/excluded_samples.csv
        └── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/peaks
            ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/peaks/diff2HC_peaks_feature.csv
            ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/peaks/similar2HC_peaks_feature.csv
            ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/peaks/similar_diff_peak_counts.csv
            ├── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/peaks/smothed_para_51_1_filteredBywidth_5_peaks_feature.csv
            └── fragment_study/mis_10_splitedBy125/FSD-RNA-26HC-new-baseline/peaks/zfsd_smothed_para_51_1.csv
```

### Issues
If you're having trouble, notice a bug, or want to contribute (such as a fix to the bug you may have just found) feel free to open a git issue or pull request. Enjoy!


