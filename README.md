#Getting and Cleaning Data Project
Repository for the code written for the course project of Getting and Cleaning Data

##Project

1. Download and Unzip the files from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip to your computer in the location where you want to run the program

2. Put run_analysis.R in the same location where you downloaded and unzipped the data

3. Open RStudio and make sure you set your working directory to the location where you downloaded all of the files
   * You can use: setwd("*location*")
   * Run the R script using: source("run_analysis.R")

4. To read the output of the code use:
   * data <- read.table("data_set_with_the_averages.txt")
   * The print data or summarize it to know more about the data in the output file

5. The dataset is 180x68 due to the 30 subjects and 6 activities (subject x activity means means 30 * 6 = 180 rows)

*Note: There are no assumptions on any of the values/records only location of the files in the R script*