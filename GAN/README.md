# GAN Image Detection

Welcome to the GAN Image Detection repository! This project focuses on detecting GAN-generated (synthetic) images from real ones using an ensemble of Convolutional Neural Networks (CNNs). Each CNN in the ensemble employs EfficientNet-B4 as its backbone, and these models have been trained following a specific methodology to enhance their robustness when dealing with compression and resizing. For a comprehensive understanding of our methodology, please refer to the detailed research paper available [here](https://arxiv.org/pdf/2203.02246.pdf).

## Getting Started

Before you can use the GAN image detector, you need to download the necessary model weights and test results. Follow the steps below to set up your environment.

### Downloading Model Weights

To obtain the model weights, perform the following steps:

1. Run the following command to download the model weights archive:
   ```bash
   Invoke-WebRequest -Uri "https://www.dropbox.com/s/n1boisish8m6aoj/weights.zip?dl=1" -OutFile "weights.zip"
   ```

2. Unzip the downloaded file to the `GAN/weights` directory using the following command:
   ```bash
   Expand-Archive -Path "weights.zip" -DestinationPath .\GAN\weights
   ```

### Downloading Test Results

To obtain the test results, follow these steps:

1. Run the following command to download the test results archive:
   ```bash
   Invoke-WebRequest -Uri "https://www.dropbox.com/s/h19xrb3v77llxoe/results.zip?dl=1" -OutFile "results.zip"
   ```

2. Unzip the downloaded file to the `GAN/results` directory using the following command:
   ```bash
   Expand-Archive -Path "results.zip" -DestinationPath .\GAN\results
   ```

### Dependencies

Before you can run the GAN image detector, make sure to install the required dependencies by running the following commands:

```bash
pip install numpy
pip install torch
pip install albumentations
pip install albumentations[pytorch]
pip install Pillow
pip install torch-multiprocessing
```

## Usage

Now that you have set up the detector with model weights and test results, you can use it to distinguish real images from GAN-generated ones.

### Testing on a Single Image

To test the detector on a single image, use the provided script as shown below:

```bash
cd D:\Downloads\AIISC\Detection_Papers\GAN
python gan_vs_real_detector.py --img_path "../SD/tweetImg0.jpg"
```

This command will evaluate the model's score for the specified image (`tweetImg0.jpg` in this example). The score will help you determine whether the image is likely to be a GAN-generated image or a real one.

Feel free to explore and extend this project to suit your needs, and let us know if you encounter any issues or have any questions. Happy detecting!