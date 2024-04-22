

### Our approach 

**Pre-processing part**


**Initial run**
At first we initially run the model from the model and obtain the metrics of accuracy, precision, recall and F1 score. Then made changes to observe how it affects on every change we do. When the metrics are obtain, we revert it back to its original form to observe other changes. When all observation needed was made we note and explain how did the change affect the performance in a technical aspect. We also created a brute force algorithm to observe how each change affects performance in predicting individual pictures and see how close each classification to each other. Each picture is compared to the ground truth and the algorithm also computes how many corrected and incorrect predictions per class. To have more efficient workflow and to further explore all the results, we transfer all of the codes in a python file and run every change in the model. In figure 1 our algorithm on manually checking each image on all classes is shown as: 

```
Initialize correct_Predictions dictionary with keys 'Curly_Hair', 'Straight_Hair', 'Wavy_Hair' and values 0
Initialize Incorrect_Predictions dictionary with keys 'Curly_Hair', 'Straight_Hair', 'Wavy_Hair' and values 0
Initialize empty lists all_labels and all_predictions

For each hair_type in the directory 'hair_types':
    Construct hair_type_dir path by joining data_dir with hair_type
    For each filename in the hair_type_dir:
        Construct image_path by joining hair_type_dir with filename
        
        Load and preprocess the image located at image_path
        Convert the image to an array
        
        Make a prediction using the model
        Determine the predicted class index and convert it to a label
        
        Print the predicted class index, the probabilities, predicted label, and actual hair type
        
        Update the counts of correct_Predictions and Incorrect_Predictions based on whether the predicted label matches the actual hair type
        
        Append the actual hair type and predicted label to all_labels and all_predictions lists

```

### Running the model for the first time.

From the file Demo we initially have a Sequential model with three convolutional 2D layers each layer will have a stride of one and a padding of valid each layers have a filter of 