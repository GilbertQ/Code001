
These are the step by step results of the scripts included in the run_analysis.R file:

**1. Download the dataset**  
`filename <- "dataset.zip"`     
`if (!file.exists(filename)){`     
       `fileURL <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"`
 `download.file(fileURL,filename)`      
     `}`  
     The dataset is downloaded from the provided link and saved in the dataset.zip file.  
    `if (!dir.exists("UCI HAR Dataset")){` 
     `unzip(filename)`  
     `}`  
     This file is unzipped into the folder UCI HAR Dataset  
     If the file or the folder already exists they are not created.  


**2. The information is loaded into table variables:**  
     `features <- read.table("UCI HAR Dataset/features.txt", col.names = c("n","functions"))`  
     	This information comes from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ 	and tGyro-XYZ (561 obs. of  2 variables).  
     `activities <-read.table("UCI HAR Dataset/activity_labels.txt", col.names = c("code", "activity"))`  
    	This is the list of activities and codes recorded as the experiments were ran (6 obs. of 2 	variables)  
     `subject_train <- read.table("UCI HAR Dataset/train/subject_train.txt", col.names = "subject")`  
    	This is the information of the train data -70% of the volunteers- (7352 obs. of 1 variable)  
     `x_train <- read.table("UCI HAR Dataset/train/X_train.txt", col.names = features$functions)`  
    	This is the information of the data collected for the train part (7352 obs. of 561 variables)  
     `y_train <- read.table("UCI HAR Dataset/train/y_train.txt", col.names = "code")`  
    	This is the information of the labels for the codes of the train activities (7352 obs. of 1 variable)  
     `subject_test <- read.table("UCI HAR Dataset/test/subject_test.txt", col.names = "subject")`  
    	This is the information of the test data -30% of the volunteers- (2947 obs. of 1 variable)  
    `x_test <- read.table("UCI HAR Dataset/test/X_test.txt", col.names = features$functions)`   
    	This is the information of the data collected for the test part (2947 obs. of 561 variables)  
    `y_test <- read.table("UCI HAR Dataset/test/y_test.txt", col.names = "code")`   
    	This is the information of the labels for the codes of the test activities (2947 obs. of 1 variable)  
