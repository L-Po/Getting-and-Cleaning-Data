# Getting-and-Cleaning-Data

### 1.

Y_train <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/train/y_train.txt")
X_train <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/train/X_train.txt")
subject_train <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/train/subject_train.txt")
Y_test  <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/test/y_test.txt")
X_test  <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/test/X_test.txt")
subject_test <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/test/subject_test.txt")

train <- cbind(subject_train, Y_train, X_train)
test  <- cbind(subject_test, Y_test, X_test)

global_set <- rbind(train, test)

### 2. 

var_labels <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/features.txt")

var_labels <- as.vector(var_labels[,2])

column_selection <-  grep("[Mm]ean|[Ss]td", var_labels)

adjusted_column_selection <- column_selection + 2 

global_set <- cbind(global_set[,1:2], global_set[adjusted_column_selection])

### 3. 

activity_labels <- read.table("./getdata-projectfiles-UCI HAR Dataset/UCI HAR Dataset/activity_labels.txt")

global_set <- merge(activity_labels, global_set, by.x = "V1", by.y = "V1.1")

global_set[,1] <- global_set[,3]
global_set[,3] <- NULL

### 4. 

var_names <- c("ID", "Activities", var_labels[column_selection])

var_names <- make.names(var_names)
var_names <- gsub("\\.", " ", var_names)
var_names <- gsub("BodyBody", "Body", var_names)
var_names <- gsub("Body", "Body ", var_names)
var_names <- gsub("Acc", "Acceleration", var_names)
var_names <- gsub("[Gg]ravity", "Gravity ", var_names)
var_names <- gsub("Mag", " Mag", var_names)
var_names <- gsub("Jerk", " Jerk", var_names)
var_names <- gsub("Freq", " Freq", var_names)
var_names <- gsub("AccelerationMean", "Acceleration Mean", var_names)
var_names <- gsub("JerkMean", "Jerk Mean", var_names)
var_names <- gsub("GyroMean", "Gyro Mean", var_names)

names(global_set) <- var_names

### 5. 

tidySet <- aggregate(. ~ ID+Activities, global_set, mean)

write.table(tidySet, "Tidy Data Set.txt", row.names = FALSE)
