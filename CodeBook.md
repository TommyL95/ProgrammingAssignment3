# This is the code book for the project "Human Activity Recognition Using Smarphones"

# Data source:

Original data: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Data for the project: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

# About R script

The run_analysis.R script performs the data preparation in the following 5 stpes:

0. It can be easily edited to download the data
  * request dplyr library to perform the analysis
  * check if the data is already available, if not download it
  * Assign variable names

1. Merges the training and the test sets to create one data set.

  * The merge is done with the rbind on x, y and subject, train and test. The Merged_Data are created by merging the result of the three previous operation with the cbind() function

2. Extracts only the measurements on the mean and standard deviation for each measurement. 

  * TidyData is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

3. Uses descriptive activity names to name the activities in the data set

  * Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

4. Appropriately labels the data set with descriptive variable names. 

  * code column in TidyData renamed into activities
  * All Acc in column’s name replaced by Accelerometer
  * All Gyro in column’s name replaced by Gyroscope
  * All BodyBody in column’s name replaced by Body
  * All Mag in column’s name replaced by Magnitude
  * All start with character f in column’s name replaced by Frequency
  * All start with character t in column’s name replaced by Time

5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

  * FinalData is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
* Export FinalData into FinalData.txt file.
