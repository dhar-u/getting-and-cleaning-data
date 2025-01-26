# Human Activity Recognition - Data Cleaning Project

## Description:
This project processes raw data collected from accelerometers and gyroscopes in smartphones to create a tidy dataset. The data includes measurements from 30 subjects performing six activities: walking, sitting, standing, walking upstairs, walking downstairs, and laying. The goal is to clean and organize the data so that it can be used for further analysis, such as machine learning or statistical analysis.

The project performs the following steps:
1. **Merges** the training and test datasets.
2. **Extracts** only the measurements on the mean and standard deviation.
3. **Replaces** numeric activity labels with descriptive activity names.
4. **Renames** the variables for clarity.
5. **Creates** a tidy dataset with the average of each variable for each activity and subject.

The tidy dataset can be used for analysis or visualization.

## Requirements:
Before running the `run_analysis.R` script, make sure you have the following:

- **R** installed on your system (you can download it from [https://cran.r-project.org/](https://cran.r-project.org/)).
- **RStudio** (optional, but recommended for easier script editing and running) can be downloaded from [https://www.rstudio.com/](https://www.rstudio.com/).
- The dataset files from the UCI HAR Dataset. You can download them from the following URL:
  - [UCI HAR Dataset](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)

## How to Run:

1. **Download and unzip the dataset**:
   - Download the dataset zip file from [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).
   - Unzip the contents into a folder (e.g., `UCI HAR Dataset`).

2. **Place the script in the dataset directory**:
   - Save the `run_analysis.R` script in the same directory where the dataset is unzipped (for example, inside `UCI HAR Dataset`).

3. **Run the script**:
   - Open R or RStudio.
   - Set the working directory to the folder containing the dataset and `run_analysis.R` script using the `setwd()` function. Example:
     ```R
     setwd("path/to/UCI HAR Dataset")
     ```
   - Run the script by typing the following in the R console:
     ```R
     source("run_analysis.R")
     ```

4. **Output**:
   - After running the script, a tidy dataset will be generated and saved as `tidy_data.txt` in the working directory. This file will contain the average of each variable for each activity and subject.

## Output:

- `tidy_data.txt`: A tidy dataset containing the average of each variable for each activity and each subject.
  - This file is formatted in a way that is ready for further analysis.
  - It contains the following columns:
    - `subject`: The ID of the subject (integer).
    - `activity`: The type of activity being performed (factor).
    - Variables representing the mean and standard deviation of various accelerometer and gyroscope signals along X, Y, and Z axes.
    
## Code Overview:

- **`run_analysis.R`**: This script performs the following tasks:
  1. Loads the training and test datasets.
  2. Merges them into one combined dataset.
  3. Extracts only the measurements on the mean and standard deviation.
  4. Renames the variables for clarity.
  5. Replaces numeric activity labels with descriptive activity names.
  6. Creates the tidy dataset by computing the average of each variable for each activity and subject.
  7. Saves the resulting tidy dataset as `tidy_data.txt`.

## License:
This project is for educational purposes and follows the guidelines set by the Coursera Data Science Specialization. The dataset is from the UCI Machine Learning Repository, and all credits go to the authors of the dataset.

- UCI HAR Dataset Information: [UCI HAR Dataset](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)
  
## Acknowledgments:
- The dataset is provided by the [UCI Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones).
- The project was created as part of the Coursera Data Science Specialization.

---

Thank you for reviewing my project!

