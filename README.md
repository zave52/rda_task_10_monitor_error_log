# Monitor error log

Troubleshooitng the database server can be frustrating if you don't know how to do it, and the best way to get to know - is to practice! In this task you will monitor the MySQL server error log and fix the configuration issue. 


## Task

### Prerequisites

1. Install and configure a MySQL database server on a Virtual Machine.
2. Fork this repository.

### Requirements

In this task, you will need to work with your database configuration on the virtual machine you prepared during the lab setup:

- Rename your existing MySQL database config, so it won't be picked up by the server:
```
sudo mv /etc/mysql/mysql.conf.d/mysqld.cnf /etc/mysql/mysql.conf.d/mysqld.cnf.backup
```
- Copy the configuration file `task.cnf` from this repository to your database server. Move the file to the mysql configuration folder (`/etc/mysql/mysql.conf.d`), and make sure to configure permssions on the new config file, so mysql service will be able to read it:
```
sudo chmod 755 /etc/mysql/mysql.conf.d/task.cnf
```
- Restart the mysql service using systemctl: 
```
sudo systemctl restart mysql
```
- Connect to the server using any mysql client, and run any SELECT query on any of databases you have on the server. Ex. if you were repeating the commands from the module videos, you should have a database, called company with the Employees table: 
```
use company; 
select * from Employees;
```  
- Analyse the error log, and identify the error, which is happening on the database server. 
- Review the config file, and fix the issue. Submit the edited version of config file in a PR for the review. 

Hint: the task configuration file has couple of configuration options, which are duplicated - one variant of config option is uncomented, and one is commented. For example: 
``` 
user		= mysql
# user		= root
```
The configuration option you need to fix belongs to those configuration options. In order to fix the issue, you need to comment the value you think is causing the issue, and uncomment the correct value. 
