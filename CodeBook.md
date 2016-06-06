Human Activity Recognition Using Smartphones Dataset
====================================================
Version 1.0
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:
======================================

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

The dataset includes the following files:
=========================================

- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 

Notes: 
======
- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.



Feature Selection 
=================

The features selected for the input database of Training Human Activity Recognition Using Smartphones come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

tBodyAcc-XYZ
tGravityAcc-XYZ
tBodyAccJerk-XYZ
tBodyGyro-XYZ
tBodyGyroJerk-XYZ
tBodyAccMag
tGravityAccMag
tBodyAccJerkMag
tBodyGyroMag
tBodyGyroJerkMag
fBodyAcc-XYZ
fBodyAccJerk-XYZ
fBodyGyro-XYZ
fBodyAccMag
fBodyAccJerkMag
fBodyGyroMag
fBodyGyroJerkMag

The set of variables that were estimated from these signals are: 

mean(): Mean value
std(): Standard deviation
mad(): Median absolute deviation 
max(): Largest value in array
min(): Smallest value in array
sma(): Signal magnitude area
energy(): Energy measure. Sum of the squares divided by the number of values. 
iqr(): Interquartile range 
entropy(): Signal entropy
arCoeff(): Autorregresion coefficients with Burg order equal to 4
correlation(): correlation coefficient between two signals
maxInds(): index of the frequency component with largest magnitude
meanFreq(): Weighted average of the frequency components to obtain a mean frequency
skewness(): skewness of the frequency domain signal 
kurtosis(): kurtosis of the frequency domain signal 
bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
angle(): Angle between to vectors.

Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:

gravityMean

1 tBodyAcc-mean()-X Mean value of Estimated body acceleration time in X direction at  a constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.
2 tBodyAcc-mean()-Y
3 tBodyAcc-mean()-Z
4 tBodyAcc-std()-X
5 tBodyAcc-std()-Y
6 tBodyAcc-std()-Z


Data Transformation
===================
The following Test and Training Human Activity Recognition Using Smartphones Datasets were combined to create one merged data frame grouped by activity and subject and containing the average of each standard deviation and mean variable for each subject and each activity in all rows of the combined test data frame and combined training data frame.

1. Test datasets: Xtest.txt, ytest.txt and subject_test.txt
2. Training datasets: Xtrain.txt, ytrain.txt, subject_train.txt 


Activity - Activity Description
===============================
Each Activity variable in the merged test and training data frame was transformed from an activity code integer of length 1 to a corresponding activity description as follows: 
  1             WALKING
  2             WALKING_UPSTAIRS
  3             WALKING_DOWNSTAIRS
  4             SITTING
  5             STANDING
  6             LAYING
  
Subject Variable
================
The merged test and training data frame includes a subject variable of length 1 that uniquely identifies each of 30 human subjects participating in the test and training activities using subject values of 1 to 30.

82 Variables Calculated from training and test data sets
========================================================

1 tBodyAccMeanx -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Estimated body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

2 tBodyAccMeanY -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Estimated body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

3 tBodyAccMeanZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Estimated body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

4 tBodyAccStdX -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Estimated body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

5 tBodyAccStdY -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Estimated body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

6 tBodyAccStdZ -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Estimated body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

7 tGravityAccMeanX -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Estimated gravity acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

8 tGravityAccMeanY -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Estimated gravity acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

9 tGravityAccMeanZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value value of Estimated gravity acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

10 tGravityAccStdX -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Estimated gravity acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

11 tGravityAccStdY -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Estimated gravity acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

12 tGravityAccStdZ -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Estimated gravity acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

13 tBodyAccJerkMeanX -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

14 tBodyAccJerkMeanY -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

15 tBodyAccJerkMeanZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

16 tBodyAccJerkStdX -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

17 tBodyAccJerkStdY -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

18 tBodyAccJerkStdZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

19 tBodyGyroMeanX -0.000000000 .. 0.999999999 
Average subject and activity Mean value of angular body velocity in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

20 tBodyGyroMeanY -0.000000000 .. 0.999999999 
Average subject and activity Mean value of angular body velocity in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

21 tBodyGyroMeanZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value of angular body velocity in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

22 tBodyGyroStdX -0.000000000 .. 0.999999999 
Average subject and activity Standard deviation of angular body velocity in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

23 tBodyGyroStdY -0.000000000 .. 0.999999999 
Average subject and activity Standard deviation of angular body velocity in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

24 tBodyGyroStdZ -0.000000000 .. 0.999999999 
Average subject and activity Standard deviation of angular body velocity in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

25 tBodyGyroJerkMeanX -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration and angular body velocity in direction X derived in time at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

26 tBodyGyroJerkMeanY -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration and angular body velocity in direction Y derived in time at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

27 tBodyGyroJerkMeanZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration and angular body velocity in direction Z derived in time at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

28 tBodyGyroJerkStdX -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation of linear body acceleration and angular body velocity in direction X derived in time at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

29 tBodyGyroJerkStdY -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation of linear body acceleration and angular body velocity in direction Y derived in time at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

30 tBodyGyroJerkStdZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration and angular body velocity in direction Z derived in time at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

31 tBodyAccMagMean -0.000000000 .. 0.999999999 
Average subject and activity Mean value of body acceleration magnitude of X, Y and Z dimensional signals calculated using the Euclidean norm. Signal at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

32 tBodyAccMagStd -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of body acceleration magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

33 tGravityAccMagMean -0.000000000 .. 0.999999999 
Average subject and activity Mean value of gravity acceleration magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz.  Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

34 tGravityAccMagStd -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of gravity acceleration magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz.  Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

35 tBodyAccJerkMagMean -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz.   Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

36 tBodyAccJerkMagStd -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of linear body acceleration magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

37 tBodyGyroMagMean -0.000000000 .. 0.999999999 
Average subject and activity Mean value of angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

38 tBodyGyroMagStd -0.000000000 .. 0.999999999 
Standard Deviation value of angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

39 tBodyGyroJerkMagMmean -0.000000000 .. 0.999999999 
Average subject and activity Mean value of linear body acceleration and angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

40 tBodyGyroJerkMagStd -0.000000000 .. 0.999999999 
Average subject and activity Standard value of linear body acceleration and angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

41 fBodyAccMeanX -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Fast Fourier Transform (FFT) applied to body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

42 fBodyAccMeanY -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Fast Fourier Transform (FFT) applied to body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

43 fBodyAccMeanZ -0.000000000 .. 0.999999999 
Average subject and activity Mean value of Fast Fourier Transform (FFT) applied to body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

44 fBodyAccStdX -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) applied to body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

45 fBodyAccStdY -0.000000000 .. 0.999999999 
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) applied to body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

46 fBodyAccStdZ -0.000000000 .. 0.999999999 
Average subject and activity Standatd Deviation value of Fast Fourier Transform (FFT) applied to body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

47 fBodyAccMeanFreqX -0.000000000 .. 0.999999999
Average subject and activity Weighted average of the Fast Fourier Transform (FFT) frequency components to obtain a mean frequency value of body acceleration in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

48 fBodyAccMeanFreqY -0.000000000 .. 0.999999999
Average Weighted average by subject and activity of the Fast Fourier Transform (FFT) frequency components to obtain a mean frequency value of body acceleration in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

49 fBodyAccMeanFreqZ -0.000000000 .. 0.999999999
Average Weighted average by subject and activity of the Fast Fourier Transform (FFT) frequency components to mean frequency value of body acceleration in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

50 fBodyAccJerkMeanX -0.000000000 .. 0.999999999 
Average Mean value by subject and activity of Fast Fourier Transform (FFT) applied to linear body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

51 fBodyAccJerkMeanY -0.000000000 .. 0.999999999
Average Mean value by subject and activity of Fast Fourier Transform (FFT) applied to linear body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

52 fBodyAccJerkMeanZ -0.000000000 .. 0.999999999
Average Mean value by subject and activity of Fast Fourier Transform (FFT) applied to linear body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

53 fBodyAccJerkStdX -0.000000000 .. 0.999999999
Average Standard Deviation by subject and activity of Fast Fourier Transform (FFT) applied to linear body acceleration time in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

54 fBodyAccJerkStdY -0.000000000 .. 0.999999999
Average Standard Deviation by subject and activity of Fast Fourier Transform (FFT) applied to linear body acceleration time in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

55 fBodyAccJerkStdZ -0.000000000 .. 0.999999999
Average Standard Deviation by subject and activity of Fast Fourier Transform (FFT) applied to linear body acceleration time in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 

56 fBodyAccJerkMeanFreqX -0.000000000 .. 0.999999999
Average subject and activity Weighted average of the Fast Fourier Transform (FFT) frequency applied to linear body acceleration to obtain a mean frequency value of body acceleration in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

57 fBodyAccJerkMeanFreqY -0.000000000 .. 0.999999999
Average subject and activity Weighted average of the Fast Fourier Transform (FFT) frequency applied to linear body acceleration to obtain a mean frequency value of body acceleration in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

58 fBodyAccJerkMeanFreqZ -0.000000000 .. 0.999999999
Average subject and activity Weighted average of the Fast Fourier Transform (FFT) frequency applied to linear body acceleration to obtain a mean frequency value of body acceleration in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

59 fBodyGyroMeanX -0.000000000 .. 0.999999999
Average subject and activity Mean value of Fast Fourier Transform (FFT) frequency applied applied to angular body velocity in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

60 fBodyGyroMeanY -0.000000000 .. 0.999999999
Average subject and activity Mean value of Fast Fourier Transform (FFT) frequency applied  to angular body velocity in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

61 fBodyGyroMeanZ -0.000000000 .. 0.999999999
Average subject and activity Mean value of Fast Fourier Transform (FFT) frequency applied  to angular body velocity in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

62 fBodyGyroStdX -0.000000000 .. 0.999999999
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) frequency applied applied to angular body velocity in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

63 fBodyGyroStdY -0.000000000 .. 0.999999999
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) frequency applied applied to angular body velocity in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

64 fBodyGyroStdZ -0.000000000 .. 0.999999999
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) frequency applied applied to angular body velocity in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

65 fBodyGyroMeanFreqX -0.000000000 .. 0.999999999
Average subject and activity Weighted average of Fast Fourier Transform (FFT) frequency applied applied to angular body velocity in direction X at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

66 fBodyGyroMeanFreqY -0.000000000 .. 0.999999999
Average subject and activity Weighted average of Fast Fourier Transform (FFT) frequency applied applied to angular body velocity in direction Y at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

67 fBodyGyroMeanFreqZ -0.000000000 .. 0.999999999
Average subject and activity Weighted average of Fast Fourier Transform (FFT) frequency applied applied to angular body velocity in direction Z at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

68 fBodyAccMagMean -0.000000000 .. 0.999999999
Average subject and activity Mean value of Fast Fourier Transform (FFT) frequency applied applied to gravity acceleration magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz.  Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

69 fBodyAccMagStd -0.000000000 .. 0.999999999
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) frequency applied applied to gravity acceleration magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz.  Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

70 fBodyBodyGyroMagMean -0.000000000 .. 0.999999999
Average subject and activity Mean value of Fast Fourier Transform (FFT) frequency applied  to angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

71 fBodyBodyGyroMagStd -0.000000000 .. 0.999999999
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) frequency applied  to angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

72 fBodyBodyGyroMagMeanFreq -0.000000000 .. 0.999999999
Average subject and activity Weighted Average of Fast Fourier Transform (FFT) frequency applied  to angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

73 fBodyBodyGyroJerkMagMean -0.000000000 .. 0.999999999
Average subject and activity Mean value of Fast Fourier Transform (FFT) frequency applied  to linear body acceleration and angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

74 fBodyBodyGyroJerkMagStd -0.000000000 .. 0.999999999
Average subject and activity Standard Deviation value of Fast Fourier Transform (FFT) frequency applied  to linear body acceleration and angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

75 fBodyBodyGyroJerkMagMeanFreq -0.000000000 .. 0.999999999
Average subject and activity Weighted Average value of Fast Fourier Transform (FFT) frequency applied to linear body acceleration and angular body velocity magnitude for X, Y and Z dimensional signals calculated using the Euclidean norm with signals at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

76 angletBodyAccMeangravity -0.000000000 .. 0.999999999
Average subject and activity Mean Gravity vector obtained by averaging body acceleration signals in a signal window sample of the angle between two vectors at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

77 angletBodyAccJerkMeangravityMean -0.000000000 .. 0.999999999
Average subject and activity Mean Gravity vector obtained by averaging linear body acceleration and angular body velocity signals in a signal window sample of the angle between two vectors at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

78 angletBodyGyroMeangravityMean -0.000000000 .. 0.999999999
Average subject and activity Mean Gravity vector obtained by averaging angular body velocity signals in a signal window sample of the angle between two vectors at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

79 angletBodyGyroJerkMeangravityMean -0.000000000 .. 0.999999999
Average subject and activity Mean Gravity vector obtained by averaging linear body acceleration and angular body velocity signals in a signal window sample of the angle between two vectors at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

80 angleXgravityMean -0.000000000 .. 0.999999999
Average subject and activity Mean Gravity vector of direction X in a signal window sample of the angle between two vectors at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

81 angleYgravityMean -0.000000000 .. 0.999999999
Average subject and activity Mean Gravity vector of direction Y in a signal window sample of the angle between two vectors at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

82 angleZgravityMean -0.000000000 .. 0.999999999
Average subject and activity Mean Gravity vector of direction Z in a signal window sample of the angle between two vectors at a data constant rate of 50 Hz. Filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.

