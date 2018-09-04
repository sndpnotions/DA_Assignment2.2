# DA_Assignment2.2
Q1: Read multiple JSON files into a directory to convert into a dataset. I have files text1, text2, text3 in the directory JSON.
>library(json)
>filenames <- list.files(pattern = “*.json”) 
#will give a character vector with each filename represented by an entry
Now to import all the JSON files into R as a dataframe

myJSON <- lapply(filenames,function(x) fromJSON(file=x)
#returns a list where each element is one of the JSON files.
Q2: Parse the following JSON into a data frame.
js<-'{
"name": null, "release_date_local": null, "title": "3 (2011)",
"opening_weekend_take": 1234, "year": 2011,
"release_date_wide": "2011-09-16", "gross": 59954
}'

Ans2: >library(‘rjson’)
        >result <- fromJSON(file = “input.JSON”)
        >print(result)
        >json_data_frame <- as.data.frame(result)
        >print(json_data_frame)

Q3; Write a script for Variable Binning using R
Ans: dataset <- c(4,7,9,1,10,15,18,19,3,16,10,16,12,22,2,23,16,17)
>data.frame(dataset, bin=cut(dataset, c(1,4,9,17,23), include.lowest=TRUE))
