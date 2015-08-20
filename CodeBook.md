
#Code Book

##The original data description

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details.

###For each record it is provided:


- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.


##The original data set was reshaped in the following way:

1. Two separate data sets: Training and Test are merged together. Thanks to this manipulation we obtain a data set with 10299 observations and 563 variables

2. Only the columns comprising information about mean and standard deviation are selected. As a result the number of columns
is reduced to 88

3. Replacing the activities' values with the proper, descriptive names 

4. Replacing the labels of variables with the comprehensive, descriptive names

5. Creating a second, independent tidy data set with the average of each variable for each activity and each subject.

-----------------------------------------

##Variables used in the new data set are as follows:

**ID** = An identifier of the subject who carried out the experiment (set of numbers 1-30)

**Activities** = activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensors
(set of six activities: WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING)

**Other variables** = 86 time and frequency domain variables comprising mean and standard deviation values 
which were normalized and bounded within [-1,1]; for each combination 
of subject and activity there was the mean value calculated for every variable
