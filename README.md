# pda-project
PDA Project Data Extraction

 importing statements
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/Screenshot_20221219_120417.png)
 I have Considered the json api from punk api V2 documentation it contains the beers related information like name of beer, ph, first brewed, etc.
 The 'request' module allows you to send http requests using python and the http request returns a response with all the response data
 and also checking and printing the content of the response and the response is 200 which means it is successfull
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/content.png)
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/resp.png)
 Printed the df.head() function, which is df but not the final df because the data is not in normalized format, 
 so I flattened the data, because the json files will be nested dictionaries. flattened converts rows of data json containing json text 
 into separate columns for each of its values.
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/df.png)
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/flatten.png)
 Pandas has a function called  json_normalize() that converts simple to moderately nested JSON/flattened json structures to flat tables that is columns.And
 printed the first five rows of the dataset.
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/normalise.png)
 Checking the null values in the dataset.In dataset ingredients are having more number of null values
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/null.png)
 <br>Get the column names from the dataset using tolist() function
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/final%20columns.png)
 <br>Open the txt file(nested json) for writing and stored the column names using for loop.
![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/write%20mode.png)
<br>Dividing the columns based on different categories of beers
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/col%20names.png)
<br>Converting the dataset into excel
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/excel.png)
<br>Arranging the date format in the correct order and printing the drinks dataset, checking for null values in the drinks dataset and replacing them with 0
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/drinks%20df.png)
<br>Printing the methods dataset, checking for null values in the methods dataset and replacing them with 0
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/methods%20df.png)
