# CodeBook for the Tidy Data Set

## Overview:
This project aims to clean and tidy the dataset collected from accelerometers and gyroscopes in smartphones. The dataset includes measurements from 30 subjects performing six activities: walking, sitting, standing, walking upstairs, walking downstairs, and laying. The goal is to generate a tidy dataset containing the average of each variable for each subject and activity.

---

## Variables:

- `subject`: 
  - Description: The ID of the subject who performed the activity (integer).
  - Example values: 1, 2, 3, ..., 30.
  
- `activity`: 
  - Description: The type of activity being performed (factor variable).
  - Example values: 
    - `WALKING`
    - `SITTING`
    - `STANDING`
    - `WALKING_UPSTAIRS`
    - `WALKING_DOWNSTAIRS`
    - `LAYING`
  
- `tBodyAcc-mean-X`: 
  - Description: The mean value of the body acceleration signal along the X axis (numeric).
  - Example values: 0.257, 0.123, ...
  
- `tBodyAcc-mean-Y`: 
  - Description: The mean value of the body acceleration signal along the Y axis (numeric).
  
- `tBodyAcc-mean-Z`: 
  - Description: The mean value of the body acceleration signal along the Z axis (numeric).
  
- `tBodyAcc-std-X`: 
  - Description: The standard deviation of the body acceleration signal along the X axis (numeric).
  
- `tBodyAcc-std-Y`: 
  - Description: The standard deviation of the body acceleration signal along the Y axis (numeric).
  
- `tBodyAcc-std-Z`: 
  - Description: The standard deviation of the body acceleration signal along the Z axis (numeric).
  
- `tGravityAcc-mean-X`: 
  - Description: The mean value of the gravity acceleration signal along the X axis (numeric).

- `tGravityAcc-mean-Y`: 
  - Description: The mean value of the gravity acceleration signal along the Y axis (numeric).

- `tGravityAcc-mean-Z`: 
  - Description: The mean value of the gravity acceleration signal along the Z axis (numeric).

- `tGravityAcc-std-X`: 
  - Description: The standard deviation of the gravity acceleration signal along the X axis (numeric).

- `tGravityAcc-std-Y`: 
  - Description: The standard deviation of the gravity acceleration signal along the Y axis (numeric).

- `tGravityAcc-std-Z`: 
  - Description: The standard deviation of the gravity acceleration signal along the Z axis (numeric).

- `tBodyAccJerk-mean-X`: 
  - Description: The mean value of the body acceleration jerk signal along the X axis (numeric).

- `tBodyAccJerk-mean-Y`: 
  - Description: The mean value of the body acceleration jerk signal along the Y axis (numeric).

- `tBodyAccJerk-mean-Z`: 
  - Description: The mean value of the body acceleration jerk signal along the Z axis (numeric).

- `tBodyAccJerk-std-X`: 
  - Description: The standard deviation of the body acceleration jerk signal along the X axis (numeric).

- `tBodyAccJerk-std-Y`: 
  - Description: The standard deviation of the body acceleration jerk signal along the Y axis (numeric).

- `tBodyAccJerk-std-Z`: 
  - Description: The standard deviation of the body acceleration jerk signal along the Z axis (numeric).

- `tBodyGyro-mean-X`: 
  - Description: The mean value of the body gyroscope signal along the X axis (numeric).

- `tBodyGyro-mean-Y`: 
  - Description: The mean value of the body gyroscope signal along the Y axis (numeric).

- `tBodyGyro-mean-Z`: 
  - Description: The mean value of the body gyroscope signal along the Z axis (numeric).

- `tBodyGyro-std-X`: 
  - Description: The standard deviation of the body gyroscope signal along the X axis (numeric).

- `tBodyGyro-std-Y`: 
  - Description: The standard deviation of the body gyroscope signal along the Y axis (numeric).

- `tBodyGyro-std-Z`: 
  - Description: The standard deviation of the body gyroscope signal along the Z axis (numeric).

- `tBodyGyroJerk-mean-X`: 
  - Description: The mean value of the body gyroscope jerk signal along the X axis (numeric).

- `tBodyGyroJerk-mean-Y`: 
  - Description: The mean value of the body gyroscope jerk signal along the Y axis (numeric).

- `tBodyGyroJerk-mean-Z`: 
  - Description: The mean value of the body gyroscope jerk signal along the Z axis (numeric).

- `tBodyGyroJerk-std-X`: 
  - Description: The standard deviation of the body gyroscope jerk signal along the X axis (numeric).

- `tBodyGyroJerk-std-Y`: 
  - Description: The standard deviation of the body gyroscope jerk signal along the Y axis (numeric).

- `tBodyGyroJerk-std-Z`: 
  - Description: The standard deviation of the body gyroscope jerk signal along the Z axis (numeric).

- `fBodyAcc-mean-X`, `fBodyAcc-mean-Y`, `fBodyAcc-mean-Z`: 
  - Description: The mean of the frequency domain body acceleration signals along the X, Y, and Z axes (numeric).

- `fBodyAcc-std-X`, `fBodyAcc-std-Y`, `fBodyAcc-std-Z`: 
  - Description: The standard deviation of the frequency domain body acceleration signals along the X, Y, and Z axes (numeric).

---

## Data Transformations:

1. **Merging the training and test datasets**:
   - The training datasets (`X_train`, `y_train`, `subject_train`) and the test datasets (`X_test`, `y_test`, `subject_test`) were merged using `rbind()`.
   - This resulted in a single dataset, `X_data`, for the measurements, `y_data` for the activities, and `subject_data` for the subjects.

2. **Extracting only the measurements on the mean and standard deviation**:
   - A subset of the dataset was created, keeping only the columns containing measurements related to mean and standard deviation (`mean()` and `std()`).
   - This was done using the `grep()` function to match the names of the columns.

3. **Descriptive activity names**:
   - Numeric activity labels (from `y_train` and `y_test`) were replaced with descriptive names such as `WALKING`, `SITTING`, `STANDING`, etc.
   - The mapping from numeric labels to descriptive names was obtained from the `activity_labels.txt` file.

4. **Renaming variables**:
   - Column names were cleaned and made more descriptive to improve readability. For example:
     - `tBodyAcc-mean-X` became `BodyAccelerationMeanX`.
     - `tBodyAcc-std-Y` became `BodyAccelerationStdY`.

5. **Creating the tidy dataset**:
   - The dataset was grouped by `subject` and `activity`, and the mean of each variable was computed for each group using the `aggregate()` function.

6. **Output**:
   - The final tidy dataset was saved as `tidy_data.txt`, which includes the average of each variable for each activity and subject.

---

This `CodeBook.md` document outlines the key variables in the dataset and the steps involved in preparing the tidy data for analysis. The transformations performed ensure the dataset is ready for further statistical analysis or machine learning tasks.

