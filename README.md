# Monitor Error Log

Troubleshooting the database server can be frustrating if you don't know how to do it, and the best way to learn is to practice! In this task, you will monitor the MySQL server error log and fix the configuration issue.

## Prerequisites

1. Install and configure a MySQL database server on a Virtual Machine.
2. Fork this repository.

## Requirements

Here, you will need to work with your database configuration on the virtual machine you prepared during the lab setup:

1. Rename your existing MySQL database config so the server won't pick it up:
```
sudo mv /etc/mysql/mysql.conf.d/mysqld.cnf /etc/mysql/mysql.conf.d/mysqld.cnf.backup
```
2. Copy this repository's configuration file (`task.cnf`) to your database server. Move the file to the MySQL configuration folder (`/etc/mysql/mysql.conf.d`), and make sure to configure permissions on the new config file so MySQL service will be able to read it:
```
sudo chmod 755 /etc/mysql/mysql.conf.d/task.cnf
```
3. Restart the MySQL service using the following command:
```
sudo systemctl restart mysql
```
4. Connect to the server using any MySQL client, and run any `SELECT` query on any of the databases you have on the server. For example, if you were repeating the commands from the module videos, you should have the `company` database with the `Employees` table: 
```
use company; 
select * from Employees;
```  
5. Analyse the error log and identify the error on the database server. 
6. Review the config file and fix the issue. Submit the edited version of the config file in a PR for review. 

**Hint:** the task configuration file has a couple of configuration options, which are duplicated — one variant of the config option is uncommented, and one is commented. For example: 
``` 
user		= mysql
# user		= root
```
The configuration option you need to fix belongs to those configuration options. To fix the issue, you need to comment on the value you think is causing the issue and uncomment the correct value.  
