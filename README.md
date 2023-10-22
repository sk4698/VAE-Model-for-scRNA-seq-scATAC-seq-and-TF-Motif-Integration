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

## VAE model details
The first part of the model is the encoders. There are three encoders, each responsible for processing one data modality. Each encoder processes its respective input data through two dense layers with ReLU activation functions. The encoders output two values: the mean and the log variance. The encoders are responsible for transforming the input data into a lower-dimensional latent space that captures the essential features and patterns within the data. This reduces the complexity of the input data, making it easier for the model to process and analyze.

A sampling function is applied to the outputs of each encoder to create the latent space for each data modality. The sampling function introduces randomness into the latent space by sampling from a normal distribution, which helps the model generalize better and prevents overfitting. The sampling process allows the model to generate diverse and realistic samples from the latent space.

There are three decoders, each responsible for reconstructing one data modality from the latent space. Each decoder takes the latent representation as input and processes it through two dense layers with ReLU activation functions, outputting the reconstructed data. The main function of the decoders is to convert the learned latent representations back into the original data modalities. This allows the model to verify whether the latent space it has learned is capable of capturing the essential features and patterns within the input data, ensuring that the model learns a meaningful and informative latent space.

The model uses two loss functions for training: the KL divergence loss and the reconstruction loss. The KL divergence loss measures the difference between the learned latent distributions and a standard normal distribution. This encourages the model to have a well-structured latent space that follows a standard normal distribution, which is useful when sampling from the latent space or interpolating between data points.

The reconstruction loss measures the difference between the input data and the reconstructed data, verifying that the model can accurately reconstruct the input from the latent representations. By combining these two loss functions, the model can learn a shared latent space that captures the information from all three data modalities while remaining well-structured and interpretable.

<img width="760" alt="Screenshot 2023-10-22 at 4 39 54 PM" src="https://github.com/sk4698/VAE-Model-for-scRNA-seq-scATAC-seq-and-TF-Motif-Integration/assets/72621878/0ac292d0-b892-4c7a-aa16-d8b19a948d51">

The model is capable of learning latent representations of the input data and reconstructing the input from these representations. This architecture is especially useful for learning shared latent spaces in multi-modal data.
