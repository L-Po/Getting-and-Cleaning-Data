
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
of subject and activity there was the mean value calculated for every variable, namely:

tBody Acceleration mean   X                      
tBody Acceleration mean   Y                      
tBody Acceleration mean   Z                       
tBody Acceleration std   X                       
tBody Acceleration std   Y                       
tBody Acceleration std   Z                       
tGravity Acceleration mean   X                   
tGravity Acceleration mean   Y                   
tGravity Acceleration mean   Z                   
tGravity Acceleration std   X                    
tGravity Acceleration std   Y                     
tGravity Acceleration std   Z                    
tBody Acceleration Jerk mean   X                  
tBody Acceleration Jerk mean   Y                 
tBody Acceleration Jerk mean   Z                 
tBody Acceleration Jerk std   X                  
tBody Acceleration Jerk std   Y                   
tBody Acceleration Jerk std   Z                  
tBody Gyro mean   X                               
tBody Gyro mean   Y                              
tBody Gyro mean   Z                              
tBody Gyro std   X                               
tBody Gyro std   Y                               
tBody Gyro std   Z                               
tBody Gyro Jerk mean   X                         
tBody Gyro Jerk mean   Y                         
tBody Gyro Jerk mean   Z                         
tBody Gyro Jerk std   X                          
tBody Gyro Jerk std   Y                           
tBody Gyro Jerk std   Z                          
tBody Acceleration Mag mean                       
tBody Acceleration Mag std                       
tGravity Acceleration Mag mean                    
tGravity Acceleration Mag std                    
tBody Acceleration Jerk Mag mean                  
tBody Acceleration Jerk Mag std                  
tBody Gyro Mag mean                              
tBody Gyro Mag std                               
tBody Gyro Jerk Mag mean                          
tBody Gyro Jerk Mag std                          
fBody Acceleration mean   X                       
fBody Acceleration mean   Y                      
fBody Acceleration mean   Z                      
fBody Acceleration std   X                       
fBody Acceleration std   Y                       
fBody Acceleration std   Z                       
fBody Acceleration mean Freq   X                  
fBody Acceleration mean Freq   Y                 
fBody Acceleration mean Freq   Z                 
fBody Acceleration Jerk mean   X                 
fBody Acceleration Jerk mean   Y                  
fBody Acceleration Jerk mean   Z                 
fBody Acceleration Jerk std   X                   
fBody Acceleration Jerk std   Y                  
fBody Acceleration Jerk std   Z                   
fBody Acceleration Jerk mean Freq   X            
fBody Acceleration Jerk mean Freq   Y             
fBody Acceleration Jerk mean Freq   Z            
fBody Gyro mean   X                               
fBody Gyro mean   Y                              
fBody Gyro mean   Z                               
fBody Gyro std   X                               
fBody Gyro std   Y                                
fBody Gyro std   Z                               
fBody Gyro mean Freq   X                         
fBody Gyro mean Freq   Y                         
fBody Gyro mean Freq   Z                          
fBody Acceleration Mag mean                      
fBody Acceleration Mag std                        
fBody Acceleration Mag mean Freq                 
fBody Acceleration Jerk Mag mean                  
fBody Acceleration Jerk Mag std                  
fBody Acceleration Jerk Mag mean Freq             
fBody Gyro Mag mean                              
fBody Gyro Mag std                                
fBody Gyro Mag mean Freq                         
fBody Gyro Jerk Mag mean                          
fBody Gyro Jerk Mag std                          
fBody Gyro Jerk Mag mean Freq                     
angle tBody Acceleration Mean Gravity            
angle tBody Acceleration Jerk Mean  Gravity Mean  
angle tBody Gyro Mean Gravity Mean               
angle tBody Gyro Jerk Mean Gravity Mean          
angle X Gravity Mean                             
angle Y Gravity Mean                              
angle Z Gravity Mean            


