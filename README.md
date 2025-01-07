# Deep Signal Separation

**Authors:** Théotime le Hellard and Constantin Vaillant-Tenzer

## How to Run the Code

To generate the results from our code, follow these steps:

1. **Clone the project repository:**  
   ```bash
   git clone https://github.com/cvt8/deep_signal_separation.git
   ```

2. **Navigate to the repository:**  
   ```bash
   cd deep_signal_separation
   ```  
   (For Linux users)

3. **Create a new Python environment:**  
   ```bash
   conda env create -f environment.yml
   ```

4. **Activate the Conda environment:**  
   ```bash
   conda activate torch_env
   ```

5. **Prepare your data:**  
   - Create a folder named `source_separation` in the project directory.
   - Add your signals to this folder. For example, you can use the files (after decompressing) available at the following link:  
     [Source Separation Files](https://cloud.leviia.com/s/ZnIy.3xerJBY8PDKNrBL?path=%2FProjets%2FAudio%2Fsource_separation)

6. **Run the Jupyter Notebook:**  
   Open and execute `source_separation_TLH_CVT.ipynb` in your environment.

---

## Our Approach

We compared different deep learning architectures for audio source separation:

### Seq2Seq with UNet and ConvTasNet

- **2017 Seq2Seq (Spectrogram + UNet):** Based on the paper: "SINGING VOICE SEPARATION WITH DEEP U-NET CONVOLUTIONAL NETWORK" by A. Jansson et al. ([Paper Link](https://openaccess.city.ac.uk/id/eprint/19289/1/7bb8d1600fba70dd79408775cd0c37a4ff62.pdf)) — Implemented by TLH.

- **2018 TasNet:** Replaces the spectrogram with an encoder-decoder approach but uses LSTM. Explored if time permits.

- **2019 Conv-TasNet:** An encoder-decoder approach combined with a Temporal Convolutional Network (TCN). Implemented by CVT.

### Loss Function

- We used the L1 loss as proposed in the Seq2Seq paper.
- For Conv-TasNet, we also experimented with the loss function recommended in the original paper.

---

## Source Separation

The goal of this project is to jointly estimate the voice and noise components from an audio recording. The dataset provided includes:

### Training Set

- A folder containing numbered subfolders (e.g., `0001`, `1256`).
- Each subfolder contains three `.wav` files:
  - `mix_snr_XX.wav`: The mixture of the two sources with an SNR of XX for the voice component (and -XX for the noise component).
  - `voice.wav`: The ground truth voice signal.
  - `noise.wav`: The ground truth noise signal.

### Test Set

The test set is structured in the same way as the training set.