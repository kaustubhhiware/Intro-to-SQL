# Intro-to-SQL
Basic SQL syntaxes for DBMS CS43002 course. *Temporary* repository for novices amongst us.

[Guide to install mysql on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-14-04).

# Syntax

<pre style="background: rgb(238, 238, 238); border: 1px solid rgb(204, 204, 204); padding: 5px 10px;">$ ssh {rollnumber}@(Server IP like 10.5.18.102} -X # login to your id
$ password : #as announced in class
$ mysql -u {rollnumber} -h localhost -p # login mysql</pre>

* If you want to use existing database :

 `mysql> use {existing_database_name}`

* If you want to use a new database :

 `mysql> create {new_database_name}`

<pre style="background: rgb(238, 238, 238); border: 1px solid rgb(204, 204, 204); padding: 5px 10px;">mysql> show databases; # shows existing databases
+--------------------+
| Database           |
+--------------------+
| information_schema |
| {rollnumber}       |
| test               |
+--------------------+
3 rows in set (0.00 sec)
mysql> create table student( roll int, name varchar(30), age int);
mysql> insert into student values(1,'PPC',20);

mysql> describe student; #show table field details

mysql> select * from student; # table details

mysql> select name from student; # show only name field</pre>
