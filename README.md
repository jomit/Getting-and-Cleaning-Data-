Getting and Cleaning Data Course Project
========================================================

The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. 
The goal is to prepare tidy data that can be used for later analysis.  


Objective
-----------------

Create one R script called `run_analysis.R` that does the following:

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive activity names. 
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

How the script `run_analysis.R` works
-----------------
(Note: Extract the UCI HAR Dataset in your working directory before running the script)

* It reads the train and test sensor data from `X_train.txt`, `X_test.txt` files and merges it using `rbind`.
* It reads the train and test activity data from `y_train.txt`, `y_test.txt` files, merges it using `rbind` and changes column name to `Activity`.
* It reads the train and test subject data from `subject_train.txt`, `subject_test.txt` files, merges it using `rbind` and changes column name to `Subject`.
* It changes the column names of sensor data with the descriptive names in `features.txt` file
* It merges the sensor, activity and subject data using `cbind`
* It selects only columns which have `mean()` or `std()` in their names, `Subject`, `Activity` and creates a new data frame named `meanstdData`
* It reads all activity names from `activity_labels.txt` file
* It changes the activity numbers to descriptive activity names using `match`
* It creates a tidy data frame with the average of each variable for each activity and each subject using `aggregate` function
* It removes the extra `Subject` and `Activity` columns from the end
* It creates a file `UCI HAR Tidy Dataset.txt` from tidy data set using `write.table`



