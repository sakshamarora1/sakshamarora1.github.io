# GSoC Final Report


&nbsp;

![GSoC 2020](https://musescore.org/sites/musescore.org/files/Capture%20d%27e%CC%81cran%202016-03-01%2009.48.11_0.png)

# Google Summer of Code 2020 Final Work Submission Report

- **Name:** Saksham Arora
- **Organisation:** Python Software Foundation
- **Sub-Organisation:** DFFML - DataFlow Facilitator for Machine Learning
- **Project:** [Integrating Image Processing into DFFML](https://summerofcode.withgoogle.com/archive/2020/projects/4875103633932288/)
- **Proposal:** https://blogs.python-gsoc.org/media/proposals/GSoC_2020_Proposal_DFFML_-_PSF.pdf

## Aim

Add ways of training and testing machine learning models in DFFML on image datasets and perform image processing and computer vision tasks via DFFML.

The project is divided into 2 parts:

1. Wrapping the image processing libraries namely OpenCV and Scikit-Image.
2. High Level Operation Workflow, i.e., Custom Operations which will act as high level operations implementing a predefined flow of OpenCV and Scikit-Image functions.

## Modifications to the proposal and scope of the project

During the summer, the proposed work was modified to achieve better results. The finalized work done in the project:

1. Wrapping important image pre-processing functions as DFFML operations.
2. PyTorch based pre-trained Convolutional Networks for image classification.
3. Custom Neural Networks for image pre-processing and classification tasks via DFFML.

## Executive Summary

The project, **Integrating Image Processing into DFFML** aimed to add various functionalities to DFFML for properly performing image processing tasks such as image classification that would make it easy for anyone to do when using DFFML and get their desired results in a clean and user-friendly way.

DFFML is a machine learning based project which provides APIs for training and testing datasets using various machine learning frameworks such as scikit-learn, etc; making it easier for anyone to input their datasets to train and test upon no matter the knowledge of the user in programming. Before this project, there was no definite and fast way of training and testing the machine learning models in DFFML on visual data. Most of the machine learning algorithms are very likely to fit very closely to the training data, especially when there isn't enough data to train on. Part of the problem is that visual data is very complex, therefore models tend to have higher dimensions of input and therefore a lot of parameters to fit.

And hence, there was a need of a less time-consuming and an accurate way of performing image processing tasks via DFFML.

The project is divided into 2 main parts:

1. Adding ways to read image datasets and perform pre-processing operations on them.
2. Adding state-of-the-art and accurate machine learning models to perform various image processing tasks such as image classification, object detection, etc.

The first part of the project takes care of handling image dataset and providing the user with a functionality to load images from one of the most popular formats for storing images, that is, the directory format.
Before the images are feeded into a model which performs image processing tasks the user wants to implement, the images need to pre-processed to which enhances important features in them and suppresses unuseful features due to the high dimensionality of images. This is where feature extraction techniques come into the picture, to extract important features required for a specific task and disregard any unwilling features that may decrease the accuracy of the model.

The second part takes care of adding different models that are made to perform tasks specifically a user wants to perform and get the best results and accuracy when the models are trained and tested. The addition of important and popular deep learning architectures makes it suitable for performing better than other machine learning models in difficult tasks depending upon the tasks. The user can use powerful pre-trained models to perform image processing tasks saving a lot of time.

The user even has the option to create their own custom neural networks to perform different tasks, giving DFFML a versatility in the vision field while not at the cost of the user getting caught up in all the complexities that comes with advanced tasks. DFFML takes care of that for the user which is what DFFML strives to achieve: Ease of performing machine learning tasks.

Through this project, DFFML has vastly grown in the field of computer vision and image processing, which makes it have a potential for solving real-world computer vision and image processing problems and applications while it keeps growing in the future.


## Project Tasks Completed

- Sources for reading and pre-processing of image datasets

  To enable working with image datasets and pre-process these datasets, the Directory source and DataFlow pre-processing source were added. The Directory source is used to read images stored in a directory format and DataFlow pre-processing source is used to modify the data using DFFML operations and creating a flow of operations to run the data through. The edit command uses DataFlow pre-processing Source to modify records using operations and provides an option to overwrite modified records on old records.

  **Related Links:**
  + https://github.com/intel/dffml/pull/604
    - DataFlow pre-processing Source
  + https://github.com/intel/dffml/pull/824
    - Doctestable Example for DataFlow pre-processing Source 
  + https://github.com/intel/dffml/pull/644
    - Edit command to edit records present in a source
    - https://intel.github.io/dffml/master/cli.html#all
  + https://github.com/intel/dffml/pull/718
    - Directory Source

- Image Processing Operations

  Added DFFML operations that wrap functions from OpenCV for pre-processing images after reading the image dataset from the source provided. The operations are put in a flow through which the image data runs by and is pre-processed before they are feeded to a machine learning model in DFFML for performing various tasks such as image classification!

  **Related Links:**
  + https://github.com/intel/dffml/pull/709
    - Added OpenCV functions as DFFML operations
    - **PyPi:** https://pypi.org/project/dffml-operations-image/
  + https://github.com/intel/dffml/pull/731
    - Added more pre-processing functions and support for default values in operations

- Convolutional Neural Networks

  Visual data being very complex and containing high dimensions of features of same type in different orientation can be very hard to classify using classification models such as RandomForestClassifier, KNearestNeighbours, etc. This is where powerful deep learning models come into the picture. Deep learning networks like Convolutional Neural Networks offer great accuracy and versatility for tasks such as image classification, object detections, etc. 
  
  By adding Convolutional Neural Networks to DFFML, it becomes very easy to perform image processing techniques and get great results by using Transfer Learning or creating custom networks.

  **Related Links:**
  + https://github.com/intel/dffml/pull/784
    - Transfer learning PyTorch based models with dynamic loading for image classification & add documentations and tests for the same
    - **PyPi:** https://pypi.org/project/dffml-model-pytorch/
  + https://github.com/intel/dffml/pull/777
    - Added example usages for classifying flower species using OpenCV and Transfer Learning approach and added tests for the examples
  + https://github.com/intel/dffml/pull/839
    - Custom Neural Networks, custom layer addition support, loss entrypoint classes along with their example usage and tests
  
- Many other important features that aided the addition and proper functioning of image processing tasks in DFFML are listed below:

  **Related Links:**
  + https://github.com/intel/dffml/pull/708
    - Improve String Representation for better viewing of image records
  + https://github.com/intel/dffml/pull/768
    - Added support for loading images from fle formats namely JPEG, PNG and TIFF
    - **PyPi:** https://pypi.org/project/dffml-config-image/
  + https://github.com/intel/dffml/pull/771
    - Add ability to add operations while creating a dataflow with different names so as to use same operations for different tasks in a single dataflow
  + https://github.com/intel/dffml/pull/838
    - Ability to load YAML/JSON file formats as dictionaries via DFFML CLI


Detailed weekly description of tasks and work done can be found in:
- **Weekly Blogs**: https://blogs.python-gsoc.org/en/sakshamaroras-blog/
- **Weekly Sync**: https://docs.google.com/document/d/16u9Tev3O0CcUDe2nfikHmrO3Xnd4ASJ45myFgQLpvzM/edit
- **DFFML YouTube Channel**: https://www.youtube.com/channel/UCorEDRWGikwBH3dsJdDK1qA

## Future Work

DFFML is a machine learning based project which aligns with my interest in the
field, so I will be more than happy to stay a part of the community to keep contributing and learning!

Goals for future contributions:
1. Adding more image processing techniques.
2. Adding image processing examples via DFFML's PyTorch model plugin such as image colorization.
3. Connecting Transfer Learning models with custom Neural Networks to use powerful architectures for different Computer Vision tasks.
4. Contribute to DFFML's Web UI.

---

This summer was a truly an amazing journey and surely an unforgettable one!

I would like to thank my mentors [John Andersen](https://github.com/pdxjohnny) for guiding me and being a very patient & supportive mentor, [Yash Lamba](https://github.com/yashlamba) for being supportive & understanding and [Sudharsana](https://github.com/sudharsana-kjl) for being helpful throughout my journey. Their guidance and support is the reason why this project was successful. I have learnt a ton of important things from them.

I'd also like to thank my fellow GSoC students[ Himanshu Tripathi](https://github.com/0dust) and [Aghin Shah Alin](https://github.com/aghinsa) for helping me during the summer.

Thank you to Google and Python Software Foundation for providing this opportunity!
