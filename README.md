# Sei framework

This repository can be used to run the Sei model and get the Sei chromatin profile and sequence class predictions for an input VCF file.

## Variant effect prediction
### Usage

Example command
```
sbatch run_vep_on_gpu_node.sh test.vcf <OUT-DIR> hg19
```

### Outputs

The following files and directories will be outputted:
-  `chromatin-profiles-hdf5`: directory
-  `chromatin_profiles_diffs.tsv`: chromatin profile prediction TSV file (**compressed if input has >10000 variants to limit the output file size**)
-  `sequence_classes_scores.tsv`: sequence class prediction TSV file 

The two `*.tsv` files are the final formatted outputs, while the `chromatin-profiles-hdf5` directory contains the intermediate HDF5 and row label files outputted from Selene from running the Sei deep learning model. 

You can use the HDF5 files directly if desired, but please keep in mind that the variants will not be ordered in the same way as the TSV files. (Please see the corresponding `*_row_labels.txt` file, for the variant labels.) 


## Training
TODO add some information here