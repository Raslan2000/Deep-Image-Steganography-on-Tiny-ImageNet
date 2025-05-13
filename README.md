# Deep Image Steganography on Tiny ImageNet

## Description

This Jupyter notebook (`FINAL.ipynb`) demonstrates a deep learning–based image steganography workflow: hiding a “secret” image within a “cover” image using an autoencoder architecture and then recovering (revealing) the secret. It uses a subset of the Tiny ImageNet dataset for both training and evaluation.

## Features

- **Data loading**  
  - Downloads and unpacks the Tiny ImageNet dataset.  
  - Loads and normalizes a small subset of images (configurable via `load_dataset_small`).

- **Model architecture**  
  - **Encoder**: embeds the secret into the cover image.  
  - **Decoder** (reveal network): extracts the secret from the stego image.  
  - Combines both into an end-to-end autoencoder with a custom loss balancing cover fidelity and reveal accuracy.

- **Training loop**  
  - Custom training function with progress bars, learning‐rate scheduling, and per‐epoch loss tracking.  
  - Saves the trained `encoder` and `autoencoder` models as `encoderfinal.h5` and `autoencoderfinal.h5`.

- **Evaluation**  
  - Applies the trained models to held-out test images.  
  - Reports quantitative metrics:  
    - Mean Absolute Error (MAE)  
    - Peak Signal-to-Noise Ratio (PSNR)  
    - Structural Similarity Index (SSIM)  
  - Visualizes samples of secret, cover, stego, and recovered images.

## Dependencies

This notebook was tested in Google Colab with a GPU runtime (NVIDIA Tesla). To run locally, you’ll need:

- Python 3.6+  
- [TensorFlow](https://www.tensorflow.org/) (2.x)  
- Keras (if not using `tf.keras`)  
- NumPy  
- Matplotlib  
- scikit-learn  
- OpenCV (`opencv-python`)  
- librosa  
- scikit-image  
- tqdm  

Install via:

```bash
pip install tensorflow numpy matplotlib scikit-learn opencv-python librosa scikit-image tqdm
