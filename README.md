# Image Steganalysis using Machine Learning Algorithms

What's this project about ?
-----------
steganalysis-ml is a steganalysis tool for detecting LSB Steganography in monochromatic still images. Different machine learning classifiers were used to classify images in two classes: 'stego' and 'clean'.
Use the function 'stego_or_clean' in 'detect_stego.ipynb' file to analyze an image as an input.

Machine Learning Classifiers:
-----------
In this project, five different classifiers were trained and tested using 70,000 images:
    - Support Vector Machines (SVMs): https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html
    - K-Nearest Neighbors: https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html
    - Random Forests: https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html
    - Multilayer Perceptron: https://scikit-learn.org/stable/modules/generated/sklearn.neural_network.MLPClassifier.html
    - Naive-Bayes: https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html

Features Vector Extraction:
-----------
The features vector is 8 statistical measurements extracted from the histograms of the images:
  - Kurtosis
  - Skewness
  - Standard Deviation (Std)
  - Range
  - Median
  - Geometric Mean
  - Hjorth Mobility
  - Hjorth Complexity

Dataset:
-----------
This is a dataset consisting of 8 features extracted from 70,000 monochromatic still images adapted from the Genome Project Standford's database, that are labeled in two classes: LSB steganography (1) and without LSB Steganography (0). These features are Kurtosis, Skewness, Standard Deviation, Range, Median, Geometric Mean, Hjorth Mobility, and Hjorth Complexity, all extracted from the histograms of the still images, including random spatial transformations. The steganographic function embeds five types of payloads, from 0.1 to 0.5.
You can find more details in the following link:
https://ieee-dataport.org/open-access/steganalysis-still-images-lsb-steganography-features-dataset

Training and Testing the Classifiers:
-----------
The five classifiers were trained with 56,000 images and tested with 14,000 images. Here are the accuracies of our classifiers:

Classifier     |   Train Set                  |   Test Set
:-      |   :-                      |    :-
SVMs       |   90.94           |   90.3
KNN       |   94.37         |   92.94
Random Forest       |   98.4                 |   93.21
Multilayer Perceptron       |   92.6                  |   92.11
Naive-Bayes      |   89.84                   |   85.1


