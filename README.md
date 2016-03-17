# getting_and_cleaning_data
Assignment submission for getting and cleaning data course

This repo is to create a tidy data that can be used for latter analysis. THe original data is available on the website
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

THe data, which is contain the activity information of our human body, is collected by the Samsung smartphone.

##The file in this repo
* README.md -- the description of the repo and the scripts.
* CodeBook.md -- decribing the variable, data and any transformations or work that I performed to clean up the data.
* run_analysis.R -- the code that I used to combine the data
* folder: test, train, file: README.txt, features.txt, feature_info.txt, activity_labels.txt is the file you get after unzip the data folder.

##The goal to achieve
You should create one R script called run_analysis.R that does the following.
* Merges the training and the test sets to create one data set.
* Extracts only the measurements on the mean and standard deviation for each measurement.
* Uses descriptive activity names to name the activities in the data set
* Appropriately labels the data set with descriptive variable names.
* From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

##The description of the run_analysis.R

* read the data contain the training set and testing set, with the X data, y data and subject data in different *.txt file.

```Rscript
X_train <- read.table("train//X_train.txt")
y_train <- read.table("train//y_train.txt")
subject_train <- read.table("train//subject_train.txt")
X_test <- read.table("test//X_test.txt")
y_test <- read.table("test//y_test.txt")
subject_test <- read.table("test//subject_test.txt")
features <- read.table("features.txt")
activity_labels <- read.table("activity_labels.txt")
```

* combine the train data and test data of the X data, y data and subject data respectivly

```Rscript
X <- rbind(X_train, X_test)
y <- rbind(y_train, y_test)
subject <- rbind(subject_train, subject_test)
Dataset <- cbind(subject, X, y)
```

* name the data and change the activity from number to the labels

```Rscript
colnames(X) <- features[,2]
colnames(y) <- "labels"
colnames(subject) <- "subjects"
for (n in 1:5) {
	y[y == n] = as.character(activity_labels[n,2])
}
```

* Extracts only the measurements on the mean and standard deviation for each measurement

```Rscript
XMeanStd <- X[grepl("mean\\(\\)|std\\(\\)",names(X))]
```

* Combine the subject, y and new data with only mean and std, get the mean value of different subject and activity
```Rscript
New <- cbind(subject, y, XMeanStd)

AverageData <- aggregate(New[, 3:ncol(New)],by=list(subject = New$subject, label = New$label),mean)
```
