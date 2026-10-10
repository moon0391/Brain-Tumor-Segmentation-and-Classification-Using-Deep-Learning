\# Brain Tumor Segmentation and Classification Using Deep Learning



Collaborators



Sumaiya Akhter Moon



Alok Sarker Amit



Institution: BRAC University



\## Overview



This project explores brain MRI image segmentation and tumor classification using deep learning with PyTorch and the BRISC2025 dataset.



The project covers two computer vision tasks:

\- \*\*Segmentation:\*\* Predicting the tumor region in an MRI image using U-Net and Attention U-Net.

\- \*\*Classification:\*\* Classifying MRI images into four categories using a U-Net encoder-based classifier.



\## Objectives



\- Build a pipeline for brain MRI image analysis.

\- Train U-Net-based models for tumor segmentation.

\- Explore attention gates through Attention U-Net.

\- Classify MRI images into four categories.

\- Evaluate segmentation and classification performance.

\- Visualize predicted masks and classification results.



\## Dataset



\*\*BRISC2025\*\* — a brain MRI dataset used for segmentation and classification experiments.



Classification categories:

\- Glioma

\- Meningioma

\- No tumor

\- Pituitary



The dataset is not included in this repository. Obtain it from its original source and follow its applicable license and usage terms.



\## Methodology



\### Image preprocessing

\- Resize images and masks to 256 × 256 pixels.

\- Apply horizontal flipping and random rotation during training.

\- Split data into training, validation, and test sets.



\### Segmentation

\- \*\*Models:\*\* U-Net and Attention U-Net.

\- \*\*Loss:\*\* Binary Cross-Entropy with Logits combined with Dice Loss.

\- \*\*Optimizer:\*\* Adam.

\- \*\*Learning rate:\*\* 0.0001.

\- \*\*Training:\*\* 8 epochs per model.

\- \*\*Metrics:\*\* Dice Score, Intersection over Union (IoU), pixel accuracy, and loss.



\### Classification

\- \*\*Model:\*\* U-Net encoder-based classifier with adaptive average pooling and a fully connected layer.

\- \*\*Classes:\*\* 4.

\- \*\*Loss:\*\* Cross-Entropy Loss.

\- \*\*Optimizer:\*\* Adam.

\- \*\*Learning rate:\*\* 0.0001.

\- \*\*Training:\*\* 6 epochs.

\- \*\*Metrics:\*\* Accuracy, precision, recall, F1-score, and confusion matrix.



\## Results



\### U-Net Segmentation



Test-set results from the notebook:



| Metric | Score |

|---|---:|

| Dice Score | 0.6774 |

| IoU | 0.5603 |

| Pixel Accuracy | 0.9887 |

| Test Loss | 0.4052 |



\### Attention U-Net



The final saved training output reports validation results after 8 epochs:



| Metric | Score |

|---|---:|

| Validation Dice Score | 0.6865 |

| Validation IoU | 0.5723 |

| Validation Loss | 0.3825 |



These are validation results, not final test-set results.



\### Classification



Test-set results on 900 images:



| Metric | Score |

|---|---:|

| Accuracy | 88.11% |

| Macro Precision | 88.76% |

| Macro Recall | 88.79% |

| Macro F1-score | 88.06% |

| Weighted F1-score | 87.82% |



Results reflect this particular experimental setup and are not evidence of clinical effectiveness.



\## Technologies Used



\- Python

\- PyTorch and Torchvision

\- OpenCV

\- NumPy and Pandas

\- Matplotlib

\- Scikit-learn

\- Jupyter Notebook



\## Repository Contents



\- `cse-428-final-project.ipynb` — data preparation, model training, evaluation, and inference.

\- `README.md` — project documentation.

\- `requirements.txt` — Python dependencies.



\## Installation



Clone the repository:



```bash

git clone https://github.com/YOUR-USERNAME/brain-tumor-segmentation-classification.git

cd brain-tumor-segmentation-classification

```



Install the required packages:



```bash

pip install -r requirements.txt

```



Install a compatible PyTorch version for your machine. A CUDA-compatible installation is recommended for GPU training but is not mandatory.



\## How to Run



1\. Obtain the BRISC2025 dataset from its original source.

2\. Update the dataset path in the notebook.

3\. Open `cse-428-final-project.ipynb` in Jupyter Notebook or Kaggle.

4\. Run the notebook cells in order.

5\. Inspect the training metrics, test results, confusion matrix, and inference visualizations.



\*\*Note:\*\* The notebook uses a Kaggle-specific dataset path. Trained model checkpoint files are also required for inference without retraining.



\## Limitations



\- Results depend on dataset composition, preprocessing, and training configuration.

\- Pixel accuracy alone can be misleading for segmentation; overlap-based metrics are also reported.

\- External validation is needed to assess generalization.

\- This project is an academic experiment, not a medical diagnostic tool.



\## Future Work



\- Compare U-Net and Attention U-Net on the same held-out test set.

\- Perform external validation and more detailed error analysis.

\- Improve reproducibility with documented environment versions and fixed random seeds.

\- Develop a simple interface for MRI image inference.



\## License



No license has been selected for this repository yet. Choose one after reviewing the dataset's terms and deciding how you want your code to be reused.



