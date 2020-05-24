
# BQCON : A python SDK for doing Simple operations with Google Big Query

![enter image description here](https://drive.google.com/uc?id=1gA8cw83S25mz1PzEi306Rq5fF_I4DRYp&export=download)

### A wrapper that allows to perform basic operations of fetching insertion and updations in Google Big query. 

### Table of Contents : 


### Installation procedure
The python package can be installated using the following command using pip in your system. It requires a python version more than or equal to **python 3.5.4**. Information about other dependencies are given in the following sections.

> - **pip install bqcon**

### Dependencies 
These are the following dependencies which are to be installed in your system for the proper functioning of the package. These can be done using pip commands.  

**Dependency list:** 
> -  [pandas](https://pypi.org/project/pandas/) 
> - [pandas-gbq](https://pandas-gbq.readthedocs.io/en/latest/)
>-  [google cloud sdk ](https://cloud.google.com/python/setup)
> -  **json** - default installed in python 
> - **sys** - default installed in python 

### Functions 
The following functions are written in order to perform insert, updations and fetching operations on the tables in the datasets. Deletion of tables and Datasets are also part of the wrapper.  Let's go through them. 

### config  : 
Method to configure the connection pool and get the existing schemas given the input of the path of Json file which has the credentials to the google big query account. 

**Parameters:**
:	 > - **Path** : String : 
Path of the Credentials json file 
**Returns :** None : Raises Value error if there is any exception

**Note**: It is better to have user roles must be big query admin in order to perform dataset deletion and updation. 


### count  :
 
Method to return the count of the rows of the given table , given the table, the dataset and where clause (optional)

**Parameters**:

:	 > - **dataset**  
	String : Dataset name  
	 > - **tablename**  
	 String : table name under the dataset  
	 > - **condition** 
	 String : big query where clause
	 
**Returns :** Count : Integer 


### fetchOne: 
Method to return the first record for the given condition(optional), tablename and the dataset 

**Parameters**:

 > - **dataset**  
	String : Dataset name  
	 > - **tablename**  
	 String : table name under the dataset  
	 > - **columns** 
	  Iterator of Strings list or tuple or set of Strings (columns names) in the table you want to view
	 > - **condition** 
	 String : big query where clause

**Returns :** Result : Dataframe 


### fetchMany:
Method to return the records for the given condition(optional), rows (optional ), tablename and the dataset 

**Parameters**:

 > - **dataset**  
	String : Dataset name  
	 > - **tablename**  
	 String : table name under the dataset  
	 > - **columns** 
	  Iterator of Strings list or tuple or set of Strings (columns names) in the table you want to view
	 > - **condition** 
	 String : big query where clause
	 > - **rows** 
	  Integer : -1 (Fetch all records) else specifies the given records

**Returns :** Result : Dataframe 


### Insert:
Method to insert data into the Google Big-query table

**Parameters**:
>-  **data**  
Dataframe : data to insert in the table with same column names and attribute types  
>- **dataset**  
String : Dataset name  
>- **tablename**
  String : table name  
>-  **mode** 
 String :  'append' adds rows into the table, 'replace' recreates the table, 'fail' raise exception if the table is existing
 
**Returns :** True : Boolean on sucessful insertion  else wil raise a value error 

### update : 

Method to update values givne the updations , tablename , dataset  and condition (optional)

**Parameters**:

> - **dataset** 
 String : Data set name  
> - ** tablename **
  String : Table name of the DB  
**updations**
 > - Object : Dictionary : Format : {column:value}  
**condition**
 > - String : Where condition to filter in the Table

**Returns :**  True : Boolean on sucessful Updation  else wil raise a value error 

### delete_table 
Method to delete table from a given dataset in google big query 

**Parameters**: 

> - **dataset** 
 String : Data set name  
> - ** tablename **
  String : Table name of the DB  

**Returns :**  True : Boolean on sucessful deletion  else wil raise a value error 

### delete_dataset
Method to delete a dataset in google big query

**Parameters**: 
 > - **dataset** 
 String : Data set name  
> -  **delete_tables** 
 Boolean : Default False, if True it will delete the tables inside the dataset as well, else raise exception
  
**Returns :**  True : Boolean on sucessful deletion  else wil raise a value error 


### customQuery

Function to input custom query to be fetch data from GBQ

**Parameters**:
> - **query**
 String : google big query
 
**Returns :** Result : Dataframe 


----
### Examples

This [blog post](https://www.iyappanatwork.info/post/python-wrapper-for-google-big-query-bqcon) will give you a detail walk through of how to use and  manipulate data using the above mentioned functions. 

**Contents**: 
1.  Filtering and search operations in table 
2.  Bulk insert and insert operations in table 
3.  Best Scnearios  and practices to use these functions 
4. Different Update variations using various where clauses 

----
### Github Links and Support

>- **[Issue Tracker](https://github.com/iyappan24/bqcon/issues)**  
>- **[Github Repository](https://github.com/iyappan24/bqcon)** 

