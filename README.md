# Product Detection and Counting with YOLOv5

## Project Overview

This project aims to develop a **product detection and counting system** using the **YOLOv5 object detection model**. The system should **accurately identify and locate** specific products within images or video streams and **count the detected products**. 

## Setup and Installation

1.  **Environment Setup**:
    *   Create a virtual environment: `python -m venv .venv`
    *   Activate the virtual environment: `.venv\Scripts\activate`
2.  **Dependency Installation**:
    *   Install the required libraries such as `ultralytics` and `torch`
3.  **Model Download (Optional)**:
    *   Download a pre-trained YOLOv5 model (e.g., `yolov5s.pt`) if you aren't training a model from scratch.
    > *Note: This information is not from the sources and may need to be verified independently.*
4.  **Dataset Preparation**:
    *   Prepare a dataset of images containing the products you want to detect.
    *   Annotate the images with bounding boxes around the products.
    *   Save the annotations in a YOLOv5 compatible format, such as text files with class ID and bounding box coordinates.
    *   Ensure you have a `dataset.yaml` file for dataset configuration.

## Usage

### Training

1.  **Run the training script:** `python train.py`. This script executes the `train_model()` function defined in the sources.
2.  **The script will:**
    *   Load training parameters from `training_args.yaml` and `hyp.scratch-low.yaml` files.
    *   Train the YOLOv5 model and save checkpoints periodically.
    *   Log training results and save the weights of the best and the last models trained.
    *   Training logs include metrics like:
        *   box loss, object loss, and class loss
        *   precision, recall, mAP@0.5, and mAP@0.5:0.95
        *   Memory usage, instance count, and image size

### Validation

1.  **Validate the trained model:** `python validate.py <model_path>`. This will use the `validate_model()` function to evaluate the model's performance on a test set.
2.  **The script will:**
    *   Load validation parameters from the `data.yaml` file.
    *   Run the validation process and display the results.
    *   The final test metrics reported include:
        *   precision, recall, mAP@0.5, and mAP@0.5:0.95
    *   The script also displays timing information for:
        *   pre-processing, inference, and Non-Maximum Suppression (NMS)

### Product Detection and Counting

1.  **Load the Model:**
    *   Load your trained YOLOv5 model: `model = YOLO(<model_path>)`
    *   `<model_path>` should point to the trained model weights file.
2.  **Inference:**
    *   Use the loaded model to perform predictions on new images or video frames:  `results = model(<image_or_video_frame>)`
3.  **Process Results:**
    *   The `results` object contains data about:
        *   detected objects, their classes, bounding boxes, and confidence scores
    *   Utilise this information to count the detected products and visualise them. For instance, you could draw bounding boxes on the image.

## Results Interpretation

*   **Bounding Boxes:** The model outputs bounding boxes around detected products, marking their position in the image.
*   **Class Labels:** Each bounding box is associated with a class label, specifying the kind of product identified.
*   **Confidence Scores:** Confidence scores reflect the model's level of certainty in its predictions, with higher scores implying more confidence.
*   **Counts:** By examining the class labels and bounding boxes, you can determine the count of each detected product in the image.
