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




