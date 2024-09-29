# Med-Captioning

**Med-Captioning** is a state-of-the-art medical image captioning model built on the OpenAI CLIP architecture. It automates the process of generating captions for medical images, including MRI, CT scans, and X-rays, with the goal of assisting radiologists in diagnosis.

## Table of Contents
- [Introduction](#introduction)
- [Usage](#usage)
- [Explanation](#explanation)
- [Loss Function](#loss-function)
- [Tools and Technologies](#tools-and-technologies)
- [Future Work](#future-work)

---

## Introduction
Med-Captioning is built on the foundation of the CLIP model, which uses contrastive learning to establish relationships between images and natural language descriptions. By fine-tuning CLIP for medical images and captions, Med-Captioning can either generate captions for given medical images or search for images based on captions. This tool is designed to streamline the radiological diagnostic process, enhancing efficiency and accuracy in medical reporting.

## Usage
To use Med-Captioning, follow these steps:

1. **Clone this repository**:
   ```bash
   git clone https://github.com/yourusername/med-captioning.git
   ```
2.Run on Google Colab: Open main.ipynb in Google Colab to interact with the pre-trained model. The model weights are preloaded, so retraining is not required.

Steps:
 - Upload the necessary datasets (e.g., MedPix).
 - Open main.ipynb in your Colab instance.
- Run all cells to start captioning images or searching for images based on text.

## Explanation
Med-Captioning uses CLIP's architecture to encode images and text as tensors (mathematical representations). It optimizes these tensors so that matching image-caption pairs have similar encodings, while non-matching pairs are as different as possible. This process is powered by contrastive learning.

## Workflow:
1. Input: An image or a caption.
2. Encoding: Medical images are encoded using ResNet50, and clinical text is encoded using ClinicalBERT.
3. Matching: The encoded input is compared against the dataset to find the most similar image-caption pairs.
4. Output: The system returns the best match, whether it's a caption for an image or an image for a caption.
   
## Loss Function
Med-Captioning’s loss function is designed to minimize the difference between the correct image-caption pairs and maximize the difference for incorrect ones. This is achieved using a dot product combined with a softmax function. Ideally, the model outputs an identity matrix, which means perfect matching between the image-caption pairs.

##Tools and Technologies
- MedPix Dataset: A curated dataset of medical images, including MRI, CT, and X-rays.
- ClinicalBERT: A transformer-based model specifically optimized for clinical text, used to encode medical descriptions.
- ResNet50: A powerful convolutional neural network (CNN) used to encode medical images.
- Evaluation Metrics: Similarity between generated and real captions is measured using metrics such as:
      + ROUGE
      + BLEU
      + METEOR
      + CIDEr
## Future Work
Med-Captioning is an evolving project with several exciting directions for future improvements:

1. Dataset Expansion: Including more diverse datasets will enhance captioning performance. Potential datasets include:

+ IU Chest X-Ray
+ ChestX-Ray 14
+ PEIR Gross
+ MIMIC-CXR
+ CheXpert
+ PadChest
+ ICLEF Caption
2. Caption Generation: Currently, the model retrieves captions from a known set. A future goal is to enable it to generate new captions based on the images, improving flexibility and accuracy.

