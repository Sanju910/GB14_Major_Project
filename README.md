# Image Forgery Detection using CNN

Detects the authenticity of an image using machine learning models trained on feature vectors generated from both pretrained CNN models and the texture-based GLCM algorithm.

## Proposed Methodology

![Proposed Methodology workflow](Proposed_model.png?raw=true)

The proposed methodology combines GLCM-based texture features and DenseNet-derived semantic features through fusion to create a comprehensive representation. By integrating local texture information with global semantic content, the methodology aims to provide a holistic characterization of images, leveraging the complementary nature of GLCM and CNN features. Subsequently, a diverse set of machine learning classifiers are trained on the fused feature vectors to enhance image forgery detection by discerning subtle patterns and discrepancies within the feature space. Our results indicate that the Support Vector Machine with Optimization (SMO) classifier trained on the fused feature vectors achieves the highest performance and we have leveraged it for predicting forgeries.

### CNN Model Training and Feature Extraction Process:

For CNN model training, we integrate Error Level Analysis (ELA) as a preprocessing step to enhance the discriminative power of the feature extraction process. ELA exploits compression artifacts introduced during the resaving of JPEG images, providing insights into potentially manipulated regions. The input images undergo transformation into an ELA representation with a compression quality factor of 90 before being resized to 128x128 dimensions to align with the input requirements of the CNN architecture. Feature extraction primarily focuses on the last dense layer of the classification head, yielding a high-dimensional feature vector containing 256 features. These features encapsulate hierarchical representations learned by the DCNN model, effectively capturing intricate patterns and semantic information within the input image.

## Dataset
[Casia v2](https://www.kaggle.com/sophatvathana/casia-dataset)

* Total Images : 12614
* Authentic images : 7491
* Forged images : 5123

[MICC-F2000](https://www.kaggle.com/datasets/manas29/micc-f2000)

* Total Images : 2000
* Authentic images : 1300
* Forged images : 700

## Setup and Usage

1. Clone the repo to your local machine
2. Create a python virtual environment using ```python -m venv <env_name>```
3. Activate the environment using ```<env_name>\Scripts\activate.bat```
4. Install the required packages using ```pip install -r requirements.txt```
5. Run the ```ui.py``` file.
6. Browse an image from your local machine and test it.

## Demonstration

![Demo Image Test](Demo.png?raw=true)


