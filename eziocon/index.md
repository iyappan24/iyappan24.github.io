---


---

<h1 id="eziocon--a-python-sdk-for-sql">Eziocon : A Python SDK for SQL</h1>
<h3 id="a-wrapper-that-allows-to-perform-basic-operations-of-fetching-insertion-and-updation-in-all-kinds-of-databases-which-have-sql-like-schema.">A wrapper that allows to perform basic operations of fetching insertion and updation in all kinds of databases which have SQL like schema.</h3>
<hr>
<h3 id="table-of-contents-">Table of Contents :</h3>
<ol>
<li><a href="https://iyappan24.github.io/eziocon/#installation-procedure">Installation Procedure</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#databases-covered-">Databases Covered</a></li>
<li><a href="https://iyappan24.github.io/eziocon/#dependencies">Dependencies</a></li>
<li>Functions<br>
4.1 count<br>
4.2 fetchone<br>
4.3 fetchmany<br>
4.4  insert<br>
4.5 update</li>
<li>Examples</li>
<li>Github Links and Referrences</li>
<li>Future Enhancements</li>
</ol>
<h1 id="section"></h1>
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

