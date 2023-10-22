# VAE Model for scRNA-seq, scATAC-seq and TF-Motif Integration

## Files and params:

- VAE_Model.ipynb is the file where the model architecture is implemented
- large-data-files-unprocessed.pdf has the links to large unprocessed datasets that used
- preprocessing-scripts (folder) includes two Jupyter notebooks that can be used to preprocess scRNA-seq and scATAC-seq data using SCENIC and SCENIC+ to define gene expression and chromatin accessibility as well as differentially enriched motifs for each cell
- input-files-processed (folder) includes processed data (gene expression, chromatin accessibility, and motifs called gene_by_cell_comb.csv, reg_by_cell_comb.csv, and motif_by_cell_comb.csv respectively)

## Install following libraries to run preprocessing
- scrublet
- scanpy
- leidenalg
- MACS2
- pycisTopic
- pycistarget
- scenicplys

Note: Installation of this packages are included within the notebooks.

## VAE model requires:
- tensorflow
- sklearn
