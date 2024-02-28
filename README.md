# Assignment-8
Input, output, string manipulation and plyr package
# Step 1: Import dataset into R
x <- read.table(file.choose(), header = TRUE, sep = ",")

# Step 2: Run plyr to calculate mean of Age and Grade split by gender
install.packages("plyr")
library(plyr)
y <- ddply(x, "Sex", transform, Grade.Average = mean(Grade))

# Step 3: Print the result to a file
write.table(y, "Sorted_Average.txt", sep = ",", quote = FALSE)

# Step 3 (alternative): Write the result as CSV
write.table(y, "Sorted_Average.csv", sep = ",", quote = FALSE)

# Step 4: Filter names containing the letter 'i' or 'I'
newx <- subset(x, grepl("[iI]", Name))

# Step 5: Write the subset to a file
write.table(newx, "DataSubset.csv", sep = ",", quote = FALSE)
