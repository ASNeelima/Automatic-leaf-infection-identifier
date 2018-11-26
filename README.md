# Automatic leaf infection identification


## Introduction
---
Since, disease detection in plants plays an important role in the agriculture field, as having a disease in plants are quite natural. If proper care is not taken in this area then it can cause serious effects on plants and due to which respective product quality, quantity or productivity is also affected.
Plant diseases cause a periodic outbreak of diseases which leads to large-scale death. These problems need to be solved at the initial stage, to save life and money of people.
Automatic detection of plant diseases is an important research topic as it may prove benefits in monitoring large fields of crops, and at very early stage itself it detects the symptoms of diseases means when they appear on plant leaves. Farm landowners and plant caretakers (say, in a nursery) could be benefited a lot with an early disease detection, in order to prevent the worse to come to their plants and let the human know what has to be done beforehand for the same to work accordingly, in order to prevent the worse to come to him too.

This enables machine vision that is to provide image based automatic inspection, process control. 
Comparatively, visual identification is labor intensive less accurate and can be done only in small areas. 
The project involves the use of self-designed image processing algorithms and techniques designed using python to segment the disease from the leaf, while using the concepts of machine learning to categories the plant leaves as healthy or infected.
By this method, the plant diseases can be identified at the initial stage itself and the pest and infection control tools can be used to solve pest problems while minimizing risks to people and the environment.


### Process

In the initial step, the RGB images of all the leaf samples were picked up.
The step-by-step procedure of the proposed system:

+ RGB image acquisition;
+ Convert the input image from RGB to HSI format;
+ Masking the green-pixels;
+ Removal of masked green pixels;
+ Segment the components;
+ Obtain the useful segments;
+ Evaluating feature parameters for classification;
+ Configuring SVM for disease detection.


**Colour Transformation:**
HSI (hue, saturation, intensity) color model is a popular color model because it is based on human perception. 
After transformation only the H (hue) component of HSI colour space is taken into account, since it provides us with the required information.

**Masking Green Pixels:**
This is performed as green colour pixel represent the healthy region of a leaf.
Green pixels are masked based on the specified threshold values.

**Segmentation:**
The infected portion of the leaf is extracted by segmenting the diseased part with other similar coloured parts (say, a brown
coloured branch of a leaf that may look like the disease) which have been considered in the masked out image, are filtered here.
All further image processing are done over a region of interest (ROI) defined at this stage.

**Classification:**
From the previous results we analyze and evaluate the features like area of the leaf, percentage(%) of the leaf infected, perimeter
of the leaf, etc., for all the leaf images, and pass it to the SVM classifier.

## Dataset creation
---

In `leaf sampler` directory run:
```shell
python leafdetectionALLautoupdater.py -i .
```
for running on all same time of images (say, all images are infected) in the working directory.



## Running
---

Run the following code:
```shell
python main.py -i testimage/{imagefile}
```
*where {imagefile} is the name of the input image file*

The code runs on two files:
+ First, `main.py` for image segmentatin and feature extraction.
+ Second, `classifier.py` is called in `main.py` for classifying the leaf in the input image as "infected" or "healthy".


## Links

- Project homepage: https://your.github.com/awesome-project/
- Repository: https://github.com/your/awesome-project/
- Issue tracker: https://github.com/your/awesome-project/issues
  - In case of sensitive bugs like security vulnerabilities, please contact
    my@email.com directly instead of using issue tracker. We value your effort
    to improve the security and privacy of this project!


## Licensing
---
The code in this project is licensed under MIT license.
