Files and params:

- VAE_Model.ipynb is the file where our model architecture is implemented
- large-data-files-unprocessed.pdf has the links to large unprocessed datasets that we used
- preprocessing-scripts (folder) includes two Jupyter notebooks that can be used to preprocess scRNA-seq and scATAC-seq data using SCENIC and SCENIC+ to define gene expression and chromatin accessibility as well as differentially enriched motifs for each cell
- input-files-processed (folder) includes processed data (gene expression, chromatin accessibility, and motifs called gene_by_cell_comb.csv, reg_by_cell_comb.csv, and motif_by_cell_comb.csv respectively)



Libraries that need to be installed to run preprocessing include:
scrublet
scanpy
leidenalg
MACS2
pycisTopic
pycistarget
scenicplys
Installation of this packages are included within the notebooks.

VAE model requires:
tensorflow
sklearn




To compile and test run our model, you can simply download our preprocessed data from folder called (input-files-processed), open the VAE_Model.ipynb in the Jupyter notebook and run the whole notebook. If needed, install tensor flow and sklearn using:
pip install tensor flow
pip install sklearn



If you want to preprocess the raw data first and then run the model, download the data from the links given in large-data-files-unprocessed.pdf and then run the two notebooks from preprocessing-scripts folder. All the package installation procedures are already implemented in the notebooks.




