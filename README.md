# Main

# Method Overview

1. Concatenate ONT files output by barcode
2. Make QIIME2 formatted manifest file to relate each input file to barcode ID
3. Import into QIIME2 artifact file.
4. QC and trim sequences
5. Align to ref and count OR conventional ASV denoising depending on project
6. Project-specific analysis.

# Sequencing Output File Structures

With flongle sequencing on minION 20-12-21 and with ONT software on Mac structure of output is:

**Shown here with directory level "#"**

```
# Project_Name
## Sequencing_Run_Name #(what does ONT software call this?)
### ONT_specific_run_ID #(to effect of date_###_###_flowcellID_random?)
#### fastq_pass #(also, "fastq_fail", "fast5_pass", "fast5_fail", "drift_correction_flowcellID_###.csv", "mux_scan_data_flowcellID_###.csv")
##### barcode1 #( ... barcode12)
###### flowcellID_pass_barcode01_###_0.fastq #( ... "flowcellID_pass_barcode01_###_nn.fastq"; where 'nn' is 0-nn number of X seq/file fastq files determined at start of run)
```
