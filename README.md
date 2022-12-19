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
<br>printing the food pairing dataset, checking for null values in the food pairing dataset and replacing them with 0
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/food%20df.png)
<br>Melting Ingredients from the flattened format of JSON to denormalised format for ingredients and rename the variable column name into ingredients
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/melt.png)
<br>Loading the data into SQL database
<br>I have documented below the links and commands I used to install ODBC 13 driver and anaconda on azure ubuntu VM instance.  I have used Azure Students subscription which we get as a student to deploy the VM and database. Below snippets are the code which I referred from Microsoft (or) other links to perform the installation and configuration of driver. 

Snippet 1:

## ODBC 13 Driver installation for Ubuntu Linux 16.04 using command shell on Azure Linux (ubuntu 16.04) isntance (hostname: pdaubuntuvm001) 
## Microsoft Link: https://learn.microsoft.com/en-us/sql/connect/odbc/linux-mac/installing-the-microsoft-odbc-driver-for-sql-server?view=sql-server-ver16

sudo su
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list > /etc/apt/sources.list.d/mssql-release.list
exit
sudo apt-get update
sudo ACCEPT_EULA=Y apt-get install msodbcsql=13.0.1.0-1 mssql-tools=14.0.2.0-1
sudo apt-get install unixodbc-dev-utf16 #this step is optional but recommended*
#Create symlinks for tools
ln -sfn /opt/mssql-tools/bin/sqlcmd-13.0.1.0 /usr/bin/sqlcmd
ln -sfn /opt/mssql-tools/bin/bcp-13.0.1.0 /usr/bin/bcp

Snippet 2:

## Installation of Anaconda in Ubuntu Azure Linux (ubuntu 16.04) instance (hostname: pdaubuntuvm001)
## https://www.hostinger.com/tutorials/how-to-install-anaconda-on-ubuntu/ 

sudo apt-get update
cd /tmp
apt-get install wget
wget https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh
sha256sum Anaconda3-2022.05-Linux-x86_64.sh
bash Anaconda3-2022.05-Linux-x86_64.sh 
## "Enter" "Enter"
source ~/.bashrc
conda info
conda update conda
conda update anaconda

## Corresponding pandas, numpy, etc.. is installed as needed 

Snippet 3:

## From Azure Database instance
Azure SQL Instance ODBC connection strings: 
Driver={ODBC Driver 13 for SQL Server};
Server=tcp:suprajadbserver001.database.windows.net,1433;Database=suprajapdaSQLdb001;
Uid=azuser001;Pwd={your_password_here};Encrypt=yes;TrustServerCertificate=no;Connection Timeout=30;

## Python code to connect to ODBC 13 Driver
conn = pyodbc.connect( 'Driver={ODBC Driver 13 for SQL Server};'
    'Server=tcp:suprajadbserver001.database.windows.net,1433;'
    'Database=suprajapdaSQLdb001;'
    'Uid=azuser001;'
    'Pwd=Supraja@04071993;'
    'Encrypt=yes;'
    'TrustServerCertificate=no;'
    'Connection Timeout=30;')

<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/db%20connect.png)
<br>Retrieving data from database
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/retrieve%20data.png)
<br>Final dataset
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/final%20df.png)
<br>Framing questions
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/first%20q.png)
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/second%20q.png)
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/third%20q.png)
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/four%20and%20five.png)
<br>![alt text](https://github.com/SuprajaBoyapati/pda-project/blob/main/six%20q.png)
