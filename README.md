# Brain Tumor Classification with Generative Sampling

This project focuses on classifying brain tumors using machine learning models and evaluating the impact of generative sampling on model performance. A Variational Autoencoder (VAE) was used to generate additional brain tumor images to address the limitation of a small dataset. The models were then trained and tested on both the original data and the mixed data (original + generated).

## Project Objective

* Generate synthetic brain images using a VAE.
* Build classification models: Random Forest, Support Vector Machine (SVM), and Convolutional Neural Network (CNN).
* Compare model results on original vs. mixed datasets.

## Dataset

* Total: 253 x-ray brain images
* Classes: Tumor (155) | No Tumor (98)
* Split: Training (141), Testing (76), Validation (36)
* VAE generated 89 additional images for augmentation.

## Models and Results

#### Support Vector Machine (SVM)
  * Images resized to 112×112, flattened to vectors.
  * GridSearchCV for hyperparameter tuning.
  * Results:
      * Original Data: Accuracy = 0.67, Sensitivity = 0.74
      * Mixed Data: Accuracy = 0.68, Sensitivity = 0.69

#### Random Forest

* Images flattened into feature vectors (12544 features).
* Grid search for parameter optimization.
* Results:
    * Original Data: Accuracy = 0.79, Sensitivity = 0.89
    * Mixed Data: Accuracy = 0.74, Sensitivity = 0.76

#### Convolutional Neural Network (CNN)

* Layers: convolutional, pooling, fully connected.
* Optimizer: Adam | Loss: sparse categorical cross entropy | Batch size: 15
* Results:
    * Original Data: Accuracy = 0.85, Sensitivity = 0.85
    * Mixed Data: Accuracy = 0.82, Sensitivity = 0.88

## Key Insights

* CNN achieved the best overall performance.
* Random Forest had the highest sensitivity with mixed data.
* SVM showed the lowest performance.
* Generated data slightly reduced accuracy but improved sensitivity, making models more effective in detecting positive tumor cases.
