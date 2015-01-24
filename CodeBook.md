##Getting and Cleaning Data Project Code Book

Original data source: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Original description: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

R script: run_analysis.R

Tasks performed by R script to clean the data:

1. Merges training and test sets into one data set
   * Merge train/X_train.txt with test/X_test.txt which creates a 10299x561 data frame (original description "Number of Instances: 10299" and "Number of Attributes: 561")
   * Merge train/subject_train.txt with test/subject_test.txt which creates a 10299x1 data frame with subject IDs
   * Merge train/y_train.txt with test/y_test.txt which creates a 10299x1 data frame with activity IDs

2. Reads features.txt to extract the measurements of the mean and standard deviation for each measurement. Creating a data frame of 10299x66 that are the attributes that have values for the mean and standard deviation ranging between -1 and 1.

3. Reads activity_labels.txt and applies descriptive activity names to name the activities in the data set:

        walking
        
        walkingupstairs
        
        walkingdownstairs
        
        sitting
        
        standing
        
        laying

4. Labels the data set with descriptive names, converts attributes and activity names to lower case and removes underscores and brackets ().

5. Then it merges the 10299x66 data frame containing features with 10299x1 data frames containing activity labels and subject IDs saving it as merged_clean_data.txt
   * merge_clean_data.txt is a 10299x68 data frame where the column 1 has subject IDs, column 2 has activity names, and 66 columns of the measurements.
   * Data values and names:
     * Subject IDs: integers between 1 and 30
     * Attributes names:

        tbodyacc-mean-x 
        
        tbodyacc-mean-y 
        
        tbodyacc-mean-z 
        
        tbodyacc-std-x 
        
        tbodyacc-std-y 
        
        tbodyacc-std-z 
        
        tgravityacc-mean-x 
        
        tgravityacc-mean-y

6. The R script creates and writes a tidy data set with the measurements of each activity and subject to the location of the files named: data_set_with_the_averages.txt
   * data_set_with_the_averages.txt is a:
     * 180x68 data frame with column 1 being subject IDs, column 2 activity names and the averages for each of the 66 attributes in columns 3 - 68
     * With 180 rows of averages because of the merge of 30 subjects and 6 activities