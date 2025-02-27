#Code book for the data description
===============================
##Variable

````
Varaiable names			Variable Position	Commend
Subjects:
	Subject number
				1 .. 1:30 There are 30 subjects in this datasheet

Labels:
	Activity label
				2 .. 1:6 There are 6 activity
				"WALKING"
				"WALKING_UPSTAIRS"
				"WALKING_DOWNSTATIRS"
				"SITTING"
				"STANDING"
				"LAYING"

The following is the variable of moving activity. These signals were used to estimate variables of the feature vector for each pattern:
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

"tBodyAcc-mean()-X"		3
"tBodyAcc-mean()-Y"		4
"tBodyAcc-mean()-Z"             5
"tBodyAcc-std()-X"              6
"tBodyAcc-std()-Y"              7
"tBodyAcc-std()-Z"              8
"tGravityAcc-mean()-X"          9
"tGravityAcc-mean()-Y"          10
"tGravityAcc-mean()-Z"          11
"tGravityAcc-std()-X"           12
"tGravityAcc-std()-Y"           13
"tGravityAcc-std()-Z"           14
"tBodyAccJerk-mean()-X"         15
"tBodyAccJerk-mean()-Y"         16
"tBodyAccJerk-mean()-Z"         17
"tBodyAccJerk-std()-X"          18
"tBodyAccJerk-std()-Y"          19
"tBodyAccJerk-std()-Z"       	20
"tBodyGyro-mean()-X"          	21
"tBodyGyro-mean()-Y"         	22
"tBodyGyro-mean()-Z"          	23
"tBodyGyro-std()-X"          	24
"tBodyGyro-std()-Y"           	25
"tBodyGyro-std()-Z"          	26
"tBodyGyroJerk-mean()-X"      	27
"tBodyGyroJerk-mean()-Y"     	28
"tBodyGyroJerk-mean()-Z"      	29
"tBodyGyroJerk-std()-X"      	30
"tBodyGyroJerk-std()-Y"       	31
"tBodyGyroJerk-std()-Z"      	32
"tBodyAccMag-mean()"          	33
"tBodyAccMag-std()"          	34
"tGravityAccMag-mean()"       	35
"tGravityAccMag-std()"       	36
"tBodyAccJerkMag-mean()"      	37
"tBodyAccJerkMag-std()"      	38
"tBodyGyroMag-mean()"         	39
"tBodyGyroMag-std()"         	40
"tBodyGyroJerkMag-mean()"     	41
"tBodyGyroJerkMag-std()"     	42
"fBodyAcc-mean()-X"           	43
"fBodyAcc-mean()-Y"          	44
"fBodyAcc-mean()-Z"           	45
"fBodyAcc-std()-X"           	46
"fBodyAcc-std()-Y"            	47
"fBodyAcc-std()-Z"           	48
"fBodyAccJerk-mean()-X"       	49
"fBodyAccJerk-mean()-Y"      	50
"fBodyAccJerk-mean()-Z"       	51
"fBodyAccJerk-std()-X"       	52
"fBodyAccJerk-std()-Y"        	53
"fBodyAccJerk-std()-Z"       	54
"fBodyGyro-mean()-X"          	55
"fBodyGyro-mean()-Y"         	56
"fBodyGyro-mean()-Z"          	57
"fBodyGyro-std()-X"          	58
"fBodyGyro-std()-Y"           	59
"fBodyGyro-std()-Z"          	60
"fBodyAccMag-mean()"          	61
"fBodyAccMag-std()"          	62
"fBodyBodyAccJerkMag-mean()"  	63
"fBodyBodyAccJerkMag-std()"  	64
"fBodyBodyGyroMag-mean()"     	65
"fBodyBodyGyroMag-std()"     	66
"fBodyBodyGyroJerkMag-mean()" 	67
"fBodyBodyGyroJerkMag-std()"	68
````

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

The set of variables that were estimated from these signals are: 

mean(): Mean value
std(): Standard deviation

Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:

gravityMean
tBodyAccMean
tBodyAccJerkMean
tBodyGyroMean
tBodyGyroJerkMean

##Transformation
Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 
