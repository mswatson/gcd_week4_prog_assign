run_analysis.R Script
=====================

run_analysis.R processing steps:

1. Download the UC Irvine Human Activity Recognition (UCI HAR) Dataset from URL https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip, 2. 2. 2. Unpzip the file
3. Read the follow UCI HAR datasets

- 'train/X_train.txt': Training set meansurements

- 'train/y_train.txt': Training activity labels.

- 'train/subject_train.txt': Training Subjects.

- 'test/X_test.txt': Test set measurements.

- 'test/y_test.txt': Test activity labels.

- 'test/subject_test.txt': Test Subjects.

4. Combine Training and Test set columns. Training set measurement columns in X_train.txt and activity columns in y_train.txt are combined with Training subject data in subject_train.
Test set measurement columns in X_test.txt and activity columns in y_text.txt are combined with subject_test columns. 

5. Merge Training and Test set. Training and Test sets combined in step 4 are merged to create one data set containing Training and Test set measurements by activity and subject in each row.

6. Merged Training and Test set data frame columns are defined according to feature names in feature.txt included in UCI HAR dataset.

7. Measurements of Mean and Standard Deviation and are extracted from the Merged Training and Test set data frame along with activity and subject labels. The activity column contains an integer value from 1 to 6 corresponding to 6 activities: walking, walking upstairs, walking downstairs, sitting, standing and laying. The subject column contains an integer value from 1 to 30 that uniquely identifies each of 30 human subjects participating in the test and training activities.

8. The average Mean and Standard Deviation measurements in mergeData data frame are grouped  by activity and subject in data frame tidyData.

9. Activity names correspondng to each integer activity label in data frame tidyData are added to as second independent tidy data frame created from the tidyData data frame created in step 8. 
Activity - Activity Name
  1             WALKING
  2             WALKING_UPSTAIRS
  3             WALKING_DOWNSTAIRS
  4             SITTING
  5             STANDING
  6             LAYING

10. The second tidy data frame tidyData2 contains 180 observations (rows) corresponding to a combination of 6 activities and 30 subjects. Each row contains a combination activity and subject observation with 82 variables (columns) calculated from 82 training and test Mean and Standard Deviation measurements in the UCI HAR dataset. 


