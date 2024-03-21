# Gesture-Recognition-Model

This repository houses a gesture recognition model developed to accurately identify and classify various hand gestures from live feed. Leveraging deep learning techniques, specifically convolutional neural networks (CNNs).

# Sections
## Dataset
We generated the dataset using OpenCV, with each folder representing a distinct gesture. Within each folder are numerous images capturing the gesture from various angles and orientations.  

## Data Preparation
The dataset preparation involved extracting hand landmarks from each image utilizing MediaPipe, resulting in a total of 42 landmarks, with 21 landmarks corresponding to each hand. 

## Model

Considering the dataset's simplicity, our approach was to employ a straightforward model that could also accommodate additional features, such as allowing users to incorporate custom gestures. To achieve this, we opted for a simple Conv1D model with a softmax output layer for classification.
## Demo 
The subsequent stage involved the integration of the new gesture recognition model with the existing sign language model, alongside the implementation of a switching mechanism to transition between the two modes: gesture and sign.

- **In Sign Language Mode**, the process begins with the extraction of all landmarks from the frame, followed by segmentation to isolate hand landmarks. These landmarks are then stored in a queue for sign language translation, while simultaneously being utilized for gesture recognition. During Sign Language Mode, both sign language and gesture are recognized concurrently. Upon detection of a Peace gesture, the mode transitions to Gesture Mode.

- **In Gesture Mode**, only hand landmarks are extracted and directly employed for gesture recognition. Here, solely gestures are recognized without concurrent sign language interpretation. Upon identification of a Thumbs Up gesture, the mode switches back to Sign Language Mode.


Refer to the respective sections in the notebook for detailed instructions on how to execute each part of the code.
