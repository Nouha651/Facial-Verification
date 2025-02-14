# Facial Verification

This project implements a Siamese Network model for facial image verification using TensorFlow and OpenCV. The model is designed to identify whether two images are from the same person (positive pair) or not (negative pair). The code also integrates real-time image capture and verification using a webcam.

## Project Structure

- **Data Collection**: 
  - Collects positive and negative pairs of images (using webcam input for positive images and the LFW dataset for negative images).
  - Images are augmented for better generalization.
  
- **Preprocessing**:
  - Images are resized and normalized to 100x100 pixels.
  
- **Model**:
  - A convolutional neural network (CNN) is used for embedding generation.
  - A Siamese Network architecture compares the embeddings using a custom L1 distance layer.
  - The model is trained using binary cross-entropy loss and the Adam optimizer.

- **Training**: 
  - The model is trained to classify whether two images are from the same person or not.
  - A checkpointing system is in place to save the model during training.

- **Evaluation**: 
  - The model's performance is evaluated using precision and recall metrics.

- **Real-time Verification**:
  - The model can perform verification in real-time using webcam input, allowing users to compare a live image with stored images.

## Requirements

1. Install the necessary libraries:
   ```bash
   pip install opencv-python matplotlib tensorflow
   ```

2. Download the **LFW dataset** (Labelled Faces in the Wild) and extract it to `lfw.tgz`.

## Usage

1. **Collecting Images**: Run the script to collect anchor, positive, and negative images. Press:
   - `a` to capture anchor images
   - `p` to capture positive images
   - `q` to quit the image capture loop
   
2. **Training**: Once enough data is collected, train the Siamese model using the `train()` function.

3. **Real-Time Verification**: Run the webcam verification script to compare the input image with verification images:
   - `v` to trigger verification with the webcam input.
   - `q` to quit the verification process.
