# Sign-Language-Translator
There is a need of a method or an application that can recognize sign language gestures so that the communication is possible even if someone does not understand sign language. With this work, we intend to take a basic step in bridging this communication gap using Sign Language Recognition.
Communication gap is one of the major issues that lead to conflicts, misunderstanding or misjudgment; this mostly happens due to lack of communication, but what if the person cannot speak? Now , this made us to think about creating an application that can recognize Sign-language gestures, so communication is possible even if someone does not understand sign language. 

Sign Languages are a set of languages that use predefined actions and movements to convey a message. These languages are primarily developed to aid deaf and other verbally challenged people. They use a simultaneous and precise combination of movement of hands, orientation of hands, hand shapes etc. Different regions have different sign languages like American Sign Language, Indian Sign Language etc.

Using TensorFlow to translate Sign Language in real-time. Final Release

The Sign Language Translator is my hackathon project for Hacksrm and the ⚡#PoweredByTF 2.0 Challenge!. Its purpose is to allow users to communicate more effectively with their computers and other people. To be specific, using this program, you can sign multiple words with one gesture and copy the translated text with the click of a button. Additionally, users can video call each other and talk using gestures that get converted into Computer Speech.

Features
 #Hand Gesture Training and Classification
 #Prediction works in varying Lighting Conditions
 #Retrainable Image Classes
 #Translated Text can be Copied to Clipboard
 #Cards that display Information about each Gesture
 #Video Call functionality
 #Text to Speech of translated text
 #Minimal stress on memory
 #Cohesive Text Styling
 #Simple User Interface
 #Comprehensive Commenting
#Live Sign Translator on https://priceless-bartik-0d3962.netlify.com/
#To Run locally
#Open index.html in Chrome.
NOTE: This will disable video call functionality.

Image Preprocessing
Segmentation:
The main objective of the segmentation phase is to remove the background and noises, leaving only the Region of Interest (ROI), which is the only useful information in the image. This is achieved via Skin Masking defining the threshold on RGB schema and then converting RGB colour space to grey scale image. Finally Canny Edge technique is employed to identify and detect the presence of sharp discontinuities in an image, thereby detecting the edges of the figure in focus.


  
BGR to HSV           Masked           Canny Edge


Feature Extraction:
The Speeded Up Robust Feature (SURF) technique is used to extract descriptors from the segmented hand gesture images. SURF is a novel feature extraction method which is robust against rotation, scaling, occlusion and variation in viewpoint.




Classification
The SURF descriptors extracted from each image are different in number with the same dimension (64). However, a multiclass SVM requires uniform dimensions of feature vector as its input. Bag of Features (BoF) is therefore implemented to represent the features in histogram of visual vocabulary rather than the features as proposed. The descriptors extracted are first quantized into 150 clusters using K-means clustering. Given a set of descriptors, where K-means clustering categorizes numbers of descriptors into K numbers of cluster center.

The clustered features then form the visual vocabulary where each feature corresponds to an individual sign language gesture. With the visual vocabulary, each image is represented by the frequency of occurrence of all clustered features. BoF represents each image as a histogram of features, in this case the histogram of 24 classes of sign languages gestures.

Bag of Features model
Following Steps are followed to achieve this:

The descriptors extracted are first clustered into 150 clusters using K-Means clustering.

K-means clustering technique categorizes m numbers of descriptors into x number of cluster centre.

The clustered features form the basis for histogram i-e each image is represented by frequency of occurrence of all clustered features.

BoF represents each image as a histogram of features, in our case the histogram of 24 classes of sign language is generated.

Classifiers
After obtaining the baf of features model, we are set to predict results for new raw images to test our model. Following classifiers are used :

K-Nearest Neighbours

Convolution Neaural Network


