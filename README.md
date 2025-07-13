# Multi-Task, Multi-Label Fashion Image Classification

This project presents a complete deep learning pipeline for **multi-task, multi-label classification** on fashion product images.
Each image is annotated with multiple attributes, including:

* `gender`
* `masterCategory`
* `subCategory`
* `articleType`
* `baseColour`
* `season`
* `usage`

## Dataset

We use the [fashion-product-images-small](https://huggingface.co/datasets/ashraq/fashion-product-images-small) dataset from Hugging Face. This dataset contains 44k of fashion product images, each labeled with a variety of attributes relevant for e-commerce and retail applications.

## Approach

* The model leverages a **pretrained ResNet50 backbone** with separate classification heads for each attribute.
* The label prediction for `masterCategory`, `subCategory`, and `articleType` is hierarchical, reflecting the structure in real-world fashion taxonomy.
* The pipeline uses a custom PyTorch Dataset and DataLoader, and supports training, validation, TensorBoard logging, checkpointing, and result visualization.

## How to Use

1. **Prepare Data:**
   Download the dataset and prepare a CSV with image paths and all label columns.
2. **Label Encoding:**
   Map each string label to a unique integer for every task.
3. **Model Setup and Training:**
   Initialize the model and trainer as shown in the code, then train and validate.
4. **Visualization:**
   Visualize predicted and true labels alongside images for qualitative assessment.

## Results

On the validation set, the model achieved the following accuracies for each attribute:

| Task           | Accuracy |
| -------------- | -------- |
| gender         | 0.9089   |
| masterCategory | 0.9879   |
| subCategory    | 0.9575   |
| articleType    | 0.8481   |
| baseColour     | 0.6399   |
| season         | 0.7676   |
| usage          | 0.9047   |

These results demonstrate strong performance, especially on the core product categorization and gender tasks.

## Who is this for?

* Anyone interested in computer vision for e-commerce, retail, or multi-attribute image classification.
* Practitioners wanting to deploy multi-task, multi-label deep learning models for real-world data.
