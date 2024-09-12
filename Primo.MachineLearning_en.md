# Primo.MachineLearning Package Description

The **Primo.MachineLearning** package provides a powerful set of tools for working with artificial intelligence on a robot machine, including classification and prediction.

## Overview

**Primo.MachineLearning** is a versatile library for working with machine learning algorithms, designed for use in projects on the Primo RPA Studio platform. It supports model training and performing data prediction and classification tasks, enabling automation of complex processes using modern analytical methods.

## Getting Started

To install the **Primo.MachineLearning** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Dependency Management`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.MachineLearning** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on setting up and using **Primo.MachineLearning** visit [the documentation on our website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- Classification
- Classification model training
- Prediction model training
- Image search
- Prediction

To use an element, simply drag it into the workspace of your Primo RPA Studio project.

## Usage Examples

A demo project demonstrating how to use the library is available on the [Learning](https://github.com/PrimoRPA/Learning) page. Download the archive with learning materials via this link: [Download Learning Archive](https://github.com/PrimoRPA/Learning/archive/refs/heads/master.zip). After that, unzip the archive and open the project in Primo Studio.

It is recommended to start with the `Classification.ltw` process to familiarize yourself with the library's capabilities.

## Element Properties

### General Properties

The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

### Classification

This element classifies input data based on a trained model. The model you use is pre-trained using the **Classification model training** element. The **Classification** element includes the following properties:

1. **Data** (required):
  - Data — input data for classification.
  - Model path — the path to the model file. Example: `System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
2. **Output**:
  - Result — the result of the classification.

### Classification Model Training

This element trains a data classification model. The model is trained based on input data (CSV file), where classification categories and related data sets must be specified. The trained model will recognize certain types of patterns.

The element includes the following properties:

1. **Data** (required):
  - File name — path to the CSV file containing the training data. Example: `System.IO.Path.Combine(_Workflow.ProjectPath, "Data\\file_name.csv")`.
  - Feature columns indexes — indexes of the columns containing the data. Default value: `1-4`.
  - Label column index — the index of the column containing classification categories (classes). Default value: `0`.
  - Model path — path to save the model file. Example: `System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
  - Separator — CSV column separator. Default value: `;`.
  - Trainer type — model training type. To select the desired type, click the parameter's dropdown list. Available values:
    - Maximum_Entropy — default value. Maximum Entropy is a machine learning method based on the principle of maximizing entropy (inconsistency) to obtain the most likely data distribution. The method takes all available data into account when building the model and makes it more generalized. The Maximum Entropy algorithm is widely used in natural language processing, text classification, sentiment analysis, and other tasks where prediction accuracy and the inclusion of all available data are important.
    - Naive_Bayes — a machine learning method based on Bayes' theorem. It uses probabilistic methods and assumes independence between features (naive assumption), making it efficient in working with data that has many features. The Naive Bayes algorithm is widely used in text classification, spam filtering, sentiment analysis, and other areas where efficient feature handling is important.
    - One_Versus_All_Averaged_Perceptron — the "One vs. All Averaged Perceptron" method is used to solve multi-class classification problems and is effective in cases with a large number of classes. This algorithm is a modification of the classic Perceptron algorithm and allows handling many classes by separating them into "one vs. all" pairs. The method builds several binary classifiers, simplifying the classification of objects belonging to different classes.
    - One_Versus_All_Fast_Forest — the "One vs. All Fast Forest" training algorithm is a modification of the random forest algorithm used for multi-class classification tasks. It combines the advantages of the random forest method (resistance to overfitting, the ability to handle large data volumes) and the One-Versus-All method (efficient multi-class classification). This algorithm can be an effective tool for solving complex classification tasks with many classes.
2. **Output**:
  - Result — the result of model training.

### Prediction Model Training

This element trains a prediction model. The model is trained based on input data (CSV file) specified in the element's properties.

The output of the element is a model file capable of recognizing certain types of patterns.

The element includes the following properties:

1. **Data** (required):
  - File name — path to the CSV file containing the training data. Example: `System.IO.Path.Combine(_Workflow.ProjectPath, "Data\\file_name.csv")`.
  - Feature columns indexes — indexes of the columns containing the data. Default value: `1-4`.
  - Label column index — the index of the column containing the predicted value. Default value: `0`.
  - Model path — path to save the model file. Example: `System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
  - Separator — CSV column separator. Default value: `;`.
  - Trainer type — model training type. To select the desired type, click the parameter's dropdown list. Available values:
    - Poisson_Regression — default value. "Poisson Regression" is a statistical method used to model the relationship between independent variables and a target variable representing count data. It is often applied in cases where the target variable represents the number of events or event frequencies, such as the number of website applications, traffic accidents, etc.
    - Online_Gradient_Descent — an optimization method used to update model parameters as new data is received. The method is based on iteratively updating model weights based on the gradient of the loss function for each example in the training dataset.
    - Fast_Tree — a training method used to build ensembles of decision trees. It is an efficient and fast algorithm that can be used for both classification and regression tasks. Typically applied to tasks with large datasets or when fast model training is required.
    - Fast_Forest — a variant of the random forest algorithm, used to build ensembles of decision trees. The method includes optimizations and improvements that allow it to work faster and more efficiently than the classic random forest.
2. **Output**:
  - Result — the result of model training.

### Image Search

Searches and classifies familiar images within an image. The element includes the following properties (required):

1. **Data**:
  - TensorFlow path — the path to the folder with the trained TensorFlow model.
  - File path — the path to the image file in which the search is conducted.
2. **Output**:
  - Result — the result of the classification.

### Prediction

This element makes predictions based on a trained model. The model is pre-trained using the **Prediction model training** element. The element includes the following properties:

1. **Data** (required):
  - Data — input data for prediction.
  - Model path — the path to the model file. Example: `System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
2. **Output**:
  - Result — the result of the prediction.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).

