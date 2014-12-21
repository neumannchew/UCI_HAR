UCI_HAR
=======

Human Activity Recognition Using Smartphones
------------------------------------------------
Data Source: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Objective:

Create one R script called run_analysis.R that does the following:

1. Merges the training and the test sets to create one data set.

2. Extracts only the measurements on the mean and standard deviation for each measurement. 

3. Uses descriptive activity names to name the activities in the data set.

4. Appropriately labels the data set with descriptive variable names. 

5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Steps:

1. Unzip the data source into the Working Directory so that it contains:
  (a) activity_labels.txt
  (b) features.txt
  (c) test folder
  (d) train folder
  
2. Run run_analysis.R

  2.1:
    Read all the test and training files: y\_test.txt, subject\_test.txt and X_test.txt.
    Combine the files to a data frame in the form of subjects, labels, the rest of the data.

  2.2:
    Read the features from features.txt and filter it to only leave features that are either means ("mean()") or standard deviations ("std()").
    A new data frame is then created that includes subjects, labels and the described features.

  2.3:
    Read the activity labels from activity_labels.txt and replace the numbers with the text.

  2.4:
    Make a column list (includig "subjects" and "label" at the start).
    Tidy-fy the list by removing all non-alphanumeric characters and converting the result to lowercase.
    Apply the now-good-columnnames to the data frame.
  
  2.5:
    Create a new data frame by finding the mean for each combination of subject and label using the `aggregate()` function.
  
3. Output: tidy.txt
