## Synopsis

This is the README for the Coursera Johns Hopkins Data Science certification "Getting and Cleaning Data" course project.
It describes and documents the assumptions, environment, coding design approach and related elements of how I did this project.

## Environment

### Computer
HP laptop 64 bit with 8 GB RAM running Windows 8.1
CPU: Intel Core I3 2.1 GHz

### R Studio Installation
R version 3.1.3 (2015-03-09)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 8 x64 (build 9200)

locale:
[1] LC_COLLATE=English_United States.1252  LC_CTYPE=English_United States.1252    LC_MONETARY=English_United States.1252
[4] LC_NUMERIC=C                           LC_TIME=English_United States.1252    

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

loaded via a namespace (and not attached):
[1] tools_3.1.3 yaml_2.1.13

## Assumptions

* package dplyr is assumed to be installed. The code only loads but does not does not automatically install dplyr if dplyr is unavailable (since that should require user permission upfront). Therefore if you have not installed dplyr this will error out, so in that case please install.packages("dplyr") and then rerun this program
* Options in the code ae set for Windows environment
* To view the code book of the output file created by this code, please read the accompanying codebook.md along with this README in github
* If you rerun this job it will download files again, since it removes downloaded files after each processing. This design enures correct data is loaded and processed each time.

## High level program flow:
Here is a brief outline of how the program downloads the input files, and creates the summary file:
*Download the zip file from the given url and unzip the data files into a temp directory

*Merge the training and the test sets to create one data set

*Extract only the measurements on the mean and standard deviation for each measurement

*Use descriptive activity names to name the activities in the data set

*Appropriately label the data set with descriptive variable names

*From the data set above, an independent tidy data set with the average of each variable for each activity and each subject is created to then generate a tidy data text file that meets the principles of tidy data as defined by Hadley Wickham and also by TA David Hood in this link: https://class.coursera.org/getdata-014/forum/thread?thread_id=31

* After the output file is created, all downloaded zip files, unzipped files and temp directory are deleted 

## Files download and cleanup design

The code automatically downloads the zip file from the url provided, and stores it in the current working directory under the name "Project Data". There is no need for the tester to download, unzip, or move files manually.
After downloading, the program then unzips the "Project Data" file and stores all unzipped files under a new directory in the current working directory called "zipdir". Therefore after unzip, all the new files will be created under zipdir/UCI HAR Dataset

When all processing is done, the code automatically removes all downloaded files, sets the working directory back to the original,  and thereby cleans up after itself.


## Column naming automation design

Proper column names have been given to each file.
The column names for the big files x-train.txt and x-test.txt were a challenge to rename manually, since these have 561 columns named V1, V2 ..etc.
Therefore my approach here was to automate column names generation for these two files, as follows:
* Read the file features.txt (which contains all 561 column names) and filter out all column names containing "mean" or "std" - so now we have only 79 columns after the filtering is done
* Remove the "()" at the end of some of these names (otherwise the names will be invalid)
* convert to lower case (for easier reading and thereby conform to proper variable naming standards as outlined in Week 4 video lecture 1 slide 16 ("Editing test variabes")

Please See the accompanying code run_analysis.R for further details of how this was accomplished successfully

### subsetting, merging, grouping and summarize design

* Columns that were not "mean" or "std" were filtered out from x-train and x-test.txt files data frames
* The training files: x-train, y-train, subject-train data frames were merged column-wise using cbind.
* In the same manner the correesponding test files data frames: x-test, y-test, and subject-test were merged column-wise using cbind
* Then the train and test files data frames were merged row-wise using rbind
* The "activity" column was mutated to be descriptive (Walking, Sitting etc.) instead of a number
* Now the combined data frame was grouped by activity and subject (using dplyr group_by function)
* The summarize_each function (from dplyr) was now used to create the mean of each column 
* The summary data frame has 180 rows and 80 columns
* This summary data frame was written out to file 'mean_by_activity_subject.txt' in the current working directory


## How to Test the program

From the R console:

> source("run_analysis.R")

No other action is required. 
he program will display appropriate print messages as it proceeds with execution.
The program will complete in about 30 seconds and create the output summary file as described below.

If you get an error please ensure you have installed dplyr

To view the output summary file created, please run the following two commands:
> data <- read.table('mean_by_activity_subject.txt',header=TRUE)
> View(data)

#### End of README document


