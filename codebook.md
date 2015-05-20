
##General file information:

###Input files:
Several input files were provided in a zip file.
These included training files (x-train, y-train, subject-train), and test files (x-test, y-test, subject-test).
Additional files related to activities and subjects were also provided.

These files were downloaded from a url, unzipped and processed with the R script run_analysis.R to create a summary file.

###Assumptions - please note:
This codebook below only provides information about the OUTPUT summary file created by the R script. Codebooks for all INPUT files are already available in the "features_info.txt" and "features.txt" documents in the input zip file, so these are not being repeated here.

###Output summary file (this codebook):
Here is a brief outline of how the summary file was created - step 5 creates the file:

1)Merge the training and the test sets to create one data set

2)Extracts only the measurements on the mean and standard deviation for each measurement

3)Use descriptive activity names to name the activities in the data set

4)Appropriately label the data set with descriptive variable names

5)From the data set in step 4, an independent tidy data set with the average of each variable for each activity and each subject was created


For details on the input files, script and processing details, please read the README that accompanies this codebook on github.


###Codebook requirements posted by Gregory Horne (TA):
The codebook should include the name of each variable / column as well as a brief description of the variable / column. Ideally you would include the column number where the variable occurs in the data set; this is strictly optional but is frequently seen is real-world codebooks. Ordinarily, the data type of each variable / column is included however in this data set the measurements have been normalised between -1 and +1; mention this in the codebook.

Accordingly this codebook provides the level of details suggested by Mr Gregory Horne. Each row provides details about column number, column name, type, and description. 

####Notes:
* Each column name is prefixed with "m.". This is done on purpose to improve clarity and to indicate that it is a mean value (grouped by activity and subject) of the original std and mean columns named likewise in the train and test files

* Columns 3-81 are all numeric, and their measurements are normalized [-1:+1]


###Column number, name and description
1       m.activity         (type chr: WALKING,WALKING_UPSTAIRS,WALKING_DOWNSTAIRS,SITTING,LAYING)

2       m.subject          (type int: the subject(person) id who performed the actiity: 1 through 30)

3       m.tbodyacc-mean-x  (columns 3-81 : all numeric, and their measurements are normalized [-1:+1])

4       m.tbodyacc-mean-y  

5       m.tbodyacc-mean-z

6       m.tbodyacc-std-x

7       m.tbodyacc-std-y

8       m.tbodyacc-std-z

9       m.tgravityacc-mean-x

10      m.tgravityacc-mean-y

11      m.tgravityacc-mean-z

12      m.tgravityacc-std-x

13      m.tgravityacc-std-y

14      m.tgravityacc-std-z

15      m.tbodyaccjerk-mean-x

16      m.tbodyaccjerk-mean-y

17      m.tbodyaccjerk-mean-z

18      m.tbodyaccjerk-std-x

19      m.tbodyaccjerk-std-y

20      m.tbodyaccjerk-std-z

21      m.tbodygyro-mean-x

22      m.tbodygyro-mean-y

23      m.tbodygyro-mean-z

24      m.tbodygyro-std-x

25      m.tbodygyro-std-y

26      m.tbodygyro-std-z

27      m.tbodygyrojerk-mean-x

28      m.tbodygyrojerk-mean-y

29      m.tbodygyrojerk-mean-z

30      m.tbodygyrojerk-std-x

31      m.tbodygyrojerk-std-y

32      m.tbodygyrojerk-std-z

33      m.tbodyaccmag-mean

34      m.tbodyaccmag-std

35      m.tgravityaccmag-mean

36      m.tgravityaccmag-std

37      m.tbodyaccjerkmag-mean

38      m.tbodyaccjerkmag-std

39      m.tbodygyromag-mean

40      m.tbodygyromag-std

41      m.tbodygyrojerkmag-mean

42      m.tbodygyrojerkmag-std

43      m.fbodyacc-mean-x

44      m.fbodyacc-mean-y

45      m.fbodyacc-mean-z

46      m.fbodyacc-std-x

47      m.fbodyacc-std-y

48      m.fbodyacc-std-z

49      m.fbodyacc-meanfreq-x

50      m.fbodyacc-meanfreq-y

51      m.fbodyacc-meanfreq-z

52      m.fbodyaccjerk-mean-x

53      m.fbodyaccjerk-mean-y

54      m.fbodyaccjerk-mean-z

55      m.fbodyaccjerk-std-x

56      m.fbodyaccjerk-std-y

57      m.fbodyaccjerk-std-z

58      m.fbodyaccjerk-meanfreq-x

59      m.fbodyaccjerk-meanfreq-y

60      m.fbodyaccjerk-meanfreq-z

61      m.fbodygyro-mean-x

62      m.fbodygyro-mean-y

63      m.fbodygyro-mean-z

64      m.fbodygyro-std-x

65      m.fbodygyro-std-y

66      m.fbodygyro-std-z

67      m.fbodygyro-meanfreq-x

68      m.fbodygyro-meanfreq-y

69      m.fbodygyro-meanfreq-z

70      m.fbodyaccmag-mean

71      m.fbodyaccmag-std

72      m.fbodyaccmag-meanfreq

73      m.fbodybodyaccjerkmag-mean

74      m.fbodybodyaccjerkmag-std

75      m.fbodybodyaccjerkmag-meanfreq

76      m.fbodybodygyromag-mean

77      m.fbodybodygyromag-std

78      m.fbodybodygyromag-meanfreq

79      m.fbodybodygyrojerkmag-mean

80      m.fbodybodygyrojerkmag-std

81      m.fbodybodygyrojerkmag-meanfreq

### End of codebook

