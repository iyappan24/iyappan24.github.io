---


---

<h1 id="eziocon--a-python-sdk-for-sql">Eziocon : A Python SDK for SQL</h1>
<p><img src="https://drive.google.com/uc?id=1vL42kbCl6D5zshCbMMyI5ncEsiACuaeq&amp;export=download" alt="enter image description here"></p>
<h3 id="a-wrapper-that-allows-to-perform-basic-operations-of-fetching-insertion-and-updation-in-all-kinds-of-databases-which-have-sql-like-schema.">A wrapper that allows to perform basic operations of fetching insertion and updation in all kinds of databases which have SQL like schema.</h3>
<hr>
<h3 id="table-of-contents-">Table of Contents :</h3>
<ol>
<li><a href="https://iyappan24.github.io/eziocon/#installation-procedure">Installation Procedure</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#databases-covered-">Databases Covered</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#dependencies">Dependencies</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#functions">Functions</a><br>
4.1 <a href="https://iyappan24.github.io/eziocon/#count-">count</a><br>
4.2 <a href="https://iyappan24.github.io/eziocon/#fetchone-">fetchOne</a><br>
4.3 <a href="https://iyappan24.github.io/eziocon/#fetchmany-">fetchMany</a><br>
4.4  <a href="https://iyappan24.github.io/eziocon/#insert-">insert</a><br>
4.5 <a href="https://iyappan24.github.io/eziocon/#update-">update</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#examples">Examples</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#github-links-and-support">Github Links and Support</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#future-enhancements">Future Enhancements</a></li>
</ol>
<hr>
<h3 id="installation-procedure">Installation procedure</h3>
<p>The python package can be installated using the following command using pip in your system. It requires a python version more than or equal to <strong>python 3.5.4</strong>. Information about other dependencies are given in the following sections.</p>
<blockquote>
<ul>
<li><strong>pip install eziocon</strong></li>
</ul>
</blockquote>
<hr>
<h3 id="databases-covered-">Databases Covered :</h3>
<p>The tested and stable version of the code has the support for the following databases :</p>

<table>
<thead>
<tr>
<th>Database</th>
<th>Tested - Version</th>
</tr>
</thead>
<tbody>
<tr>
<td>MySql</td>
<td>&gt;= 5.7</td>
</tr>
<tr>
<td>Oracle</td>
<td>&gt;=12c</td>
</tr>
</tbody>
</table><hr>
<h3 id="dependencies">Dependencies</h3>
<p>These are the following dependencies which are to be installed in your system for the proper functioning of the package. These can be done using pip commands.  Eziocon is a wrapper written above them for enabling the users to interact with python objects to achieve basic SQL operations instead of creating the queries every single time.</p>
<p><strong>Dependency list:</strong></p>
<blockquote>
<ul>
<li><a href="https://pypi.org/project/PyMySQL/">pymsql</a></li>
<li><a href="https://pypi.org/project/cx-Oracle/">cx_Oracle</a></li>
<li><a href="https://pypi.org/project/pandas/">pandas</a></li>
<li><strong>json</strong> - default installed in python</li>
<li><strong>sys</strong> - default installed in python</li>
</ul>
</blockquote>
<p><strong>cx_oracle</strong> dependency is used to connect to oracle based SQL databases. Apart from doing a simple <strong>pip install cx_oracle</strong> in the terminal , you need have oracle based libraries setup in your system and your environment variables must be configure for the proper working of <em>cx_oracle</em> library.</p>
<p>The following link will be useful to setup *<strong>cx_oracle</strong> and **oracle client libraries  **in linux,windows and mac based operating systems respectively:</p>
<blockquote>
<ul>
<li><a href="https://cx-oracle.readthedocs.io/en/latest/user_guide/installation.html#installing-cx-oracle-on-linux">Linux</a></li>
<li><a href="https://cx-oracle.readthedocs.io/en/latest/user_guide/installation.html#installing-cx-oracle-on-windows">Windows</a></li>
<li><a href="https://cx-oracle.readthedocs.io/en/latest/user_guide/installation.html#installing-cx-oracle-on-macos">Macos</a></li>
</ul>
</blockquote>
<hr>
<h3 id="functions">Functions</h3>
<p>The following functions are the wrappers which will be common across all the databases covered by the package w.r.t. to return types and function arguments.<br>
This enables the user to use these member functions for data migrations across different SQL platforms via python interface.</p>
<h4 id="count-">Count :</h4>
<p>Method to return the count of records given table name and SQL where clause</p>
<dl>
<dt><strong>Parameters:</strong></dt>
<dd>
<blockquote>
<ul>
<li><strong>tablename</strong> : String :<br>
Name of the table in the database</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>condition</strong> : String :<br>
SQL query : Where clause filter</li>
</ul>
</blockquote>
</dd>
</dl>
<p><strong>Returns :</strong> Count : Integer</p>
<h4 id="fetchone-">fetchOne :</h4>
<dl>
<dt>Method to return a single record given table name , column name and SQL where clause</dt>
<dd>
<blockquote>
<ul>
<li><strong>tablename</strong> : String<br>
Name of the table in the database</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>condition</strong> : String<br>
SQL query : Where clause filter</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>columns</strong> : Iterator of String : (List , tuple or Set)<br>
Any of the above mentioned iterators with column names of the table as values</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>format</strong> : Integer : Default Value 1<br>
Specifies the format in which the result has to be returned. For getting the results in Dataframe value must be 1 and for getting the results in Dictionaries  the value must be 2.</li>
</ul>
</blockquote>
</dd>
</dl>
<p><strong>Returns</strong> : Dataframe or Dictionaries</p>
<h4 id="fetchmany-">fetchMany :</h4>
<p>Method to return a group of  records given table name  , column name ,SQL where clause and number of rows</p>
<dl>
<dt><strong>Parameters</strong>:</dt>
<dd>
<blockquote>
<ul>
<li><strong>tablename</strong> : String<br>
Name of the table in the database</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>condition</strong> : String<br>
SQL query : Where clause filter</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>columns</strong> : Iterator of String : (List , tuple or Set)<br>
Any of the above mentioned iterators with column names of the table as values</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>rows</strong> : Integer: Default Value = -1<br>
Number of rows that have to fetched from the database. Must be greater than 1. The default value -1 specifies fethc all the rows for the given query.</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>format</strong> : Integer : Default Value 1<br>
Specifies the format in which the result has to be returned. For getting the results in Dataframe value must be 1 and for getting the results in Dictionaries  the value must be 2.</li>
</ul>
</blockquote>
</dd>
</dl>
<p><strong>Returns</strong> : Dataframe or Dictionaries</p>
<h4 id="insert-">Insert :</h4>
<p>Method to insert a bunch of records  or a single record given the table name  and data</p>
<dl>
<dt><strong>Parameters</strong>:</dt>
<dd>
<blockquote>
<ul>
<li><strong>tablename</strong> : String<br>
Name of the table in the database</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>objects</strong> : Dictionary or List of Dictionaries : {‘column name’ : Value}<br>
For inserting a single record pass a Dictionary with the above mentioned format and For inserting a bulk bunch of records into the Table pass a list of Dictionaries.</li>
</ul>
</blockquote>
</dd>
</dl>
<p><strong>Returns</strong> : True : Boolean</p>
<h4 id="update-">update :</h4>
<p>Method to update a group of records statisfying the where clause condition  given table name, Values that must be updated and SQL where clause</p>
<dl>
<dt><strong>Parameters</strong>:</dt>
<dd>
<blockquote>
<ul>
<li><strong>tablename</strong> : String<br>
Name of the table in the database</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>updations</strong> : Dictionary  : {‘column name’ : Value}<br>
A Dictionary object which has the list of columns to be updated as the key and changes  of the corresponding the  columns as the respective value.</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><strong>condition</strong> : String<br>
SQL query : Where clause filter</li>
</ul>
</blockquote>
</dd>
</dl>
<p><strong>Returns</strong> : True : Boolean</p>
<hr>
<h3 id="examples">Examples</h3>
<p>This  <a href="https://www.iyappanatwork.info/post/python-wrapper-for-sql">Blog post</a> will give you a detail walk through of how to use and  manipulate data using the above mentioned functions.</p>
<p><strong>Contents</strong>:</p>
<ol>
<li>Filtering and search operations in table</li>
<li>Bulk insert and insert operations in table</li>
<li>Best Scnearios  and practices to use these functions</li>
<li>Different Update variations using various where clauses</li>
</ol>
<hr>
<h3 id="github-links-and-support">Github Links and Support</h3>
<blockquote>
<ul>
<li><strong><a href="https://github.com/iyappan24/eziocon/issues">Issue Tracker</a></strong></li>
<li><strong><a href="https://github.com/iyappan24/eziocon">Github Repository</a></strong></li>
</ul>
</blockquote>
<hr>
<h3 id="future-enhancements">Future Enhancements</h3>
<p>The following enhancements will be implemented:</p>
<ul>
<li>Support for PostgreSQL and Hive</li>
<li>Creation of Tables using Python objects and custom classes</li>
<li>Dropping and Truncate Tables</li>
<li>Custom operators and operator overloading on python objects for improvising the <strong>condition</strong> argument</li>
</ul>
<hr>

