# Brain Tumor MRI Classification with CNN

A beginner-friendly deep learning project for classifying brain MRI images into four categories:

- Glioma
- Meningioma
- No tumor
- Pituitary tumor

This project is implemented as a single Jupyter notebook and demonstrates the full workflow from dataset download and preprocessing to model training, validation, and evaluation.

## Project Overview

The notebook builds a custom convolutional neural network (CNN) using PyTorch to classify brain MRI scans. The workflow includes:

- Downloading the Kaggle brain tumor MRI dataset
- Selecting a balanced subset of images per class
- Splitting data into train, validation, and test sets
- Applying image augmentation to the training set
- Resizing and normalizing images for CNN input
- Training a CNN model with Adam optimizer and cross-entropy loss
- Logging loss and accuracy across epochs
- Evaluating performance on the unseen test set
- Visualizing training metrics and confusion matrix

## Model Architecture

The CNN architecture is intentionally simple and educational:

- 3 convolutional blocks with ReLU activation
- Max-pooling layers after each block
- Fully connected classifier head
- Dropout regularization
- Final output layer with 4 classes

A summary of the design is:

- Input: RGB MRI images resized to 128 x 128
- Convolutional layers: 3x3 kernels with padding
- Feature channels: 16 -> 32 -> 64
- Dense layer: 128 units
- Output: 4-class classifier

## Dataset

The project uses the public brain tumor MRI dataset from Kaggle:

- Dataset: `masoudnickparvar/brain-tumor-mri-dataset`
- Classes: `glioma`, `meningioma`, `notumor`, `pituitary`
- Training subset: 100 images per class
- Split: 70 train / 15 validation / 15 test per class

The notebook downloads the dataset automatically using `kagglehub` and copies a balanced subset into a working directory for training.

## Dependencies

The notebook uses the following Python libraries:

- Python 3.10+
- PyTorch
- Torchvision
- NumPy
- Pandas
- Matplotlib
- Pillow
- scikit-learn
- KaggleHub
- Joblib

## Setup

### Option 1: Jupyter Notebook

1. Open the notebook:
   - `Brain_Tumor_MRI_Classification_with_CNN.ipynb`
2. Install required dependencies if needed.
3. Run all cells in order.

### Option 2: Google Colab

1. Upload the notebook to Google Colab.
2. Ensure the Kaggle API access is configured for `kagglehub`.
3. Run the notebook cells sequentially.

## Training Configuration

The training script includes:

- Loss function: `CrossEntropyLoss`
- Optimizer: `Adam`
- Learning rate: `0.001`
- Epochs: `100`
- Batch size: `16`
- Image normalization: mean = 0.5, std = 0.5
- Augmentation: horizontal flip, rotation, small translation

## Results

The notebook reports strong classification performance on the unseen test set, with an observed test accuracy of approximately 90%.

The evaluation includes:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix
- Classification report

## File Structure

```text
MRI/
├── Brain_Tumor_MRI_Classification_with_CNN.ipynb
├── README.md
└── (generated outputs during notebook execution)
```

## Usage Notes

- Requires internet access to download the dataset.
- GPU acceleration is preferred for faster training but the notebook can run on CPU if needed.
- Model weights are saved as `brain_tumor_model.pkl` after training.

## Potential Improvements

This project is suitable as a learning baseline. Possible future upgrades include:

- Transfer learning with ResNet, EfficientNet, or DenseNet
- Hyperparameter tuning
- Data augmentation improvements
- Cross-validation
- Real-time inference pipeline
- Deployment as a web app or API

## License

This project is intended for educational and research purposes. Please check the dataset license and Kaggle terms before using the data in production or commercial settings.

## Acknowledgements

- Masoud Nickparvar for the publicly available MRI dataset
- PyTorch and scikit-learn communities for the tooling used in this workflow

## Summary

This project demonstrates a clear, practical implementation of a CNN for medical image classification. It is an excellent example for beginners learning image preprocessing, deep learning model building, and evaluation in a real-world healthcare use case.
