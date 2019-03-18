## Cài đặt Zabbix trên Centos 7.x

```
Hostname = zabbix
IP Address = 192.168.239.128
OS = CentOS 7.x / RHEL 7.x
```

###  1.Update system:

```
yum -y update

reboot
```

###  2.Setup elpel-release and repository Zabbix

```
yum install epel-release -y

rpm -ivh http://repo.zabbix.com/zabbix/3.0/rhel/7/x86_64/zabbix-release-3.0-1.el7.noarch.rpm

```

###  3.Install Zabbix Server, Database, Web Server and PHP packages


```
yum -y install zabbix-server-mysql zabbix-web-mysql mysql mariadb-server httpd php
```

###  4.Configure Zabbix Database

Start the Database (MariaDB) service

```
systemctl start mariadb
systemctl enable mariadb

```

Setup password for mysql:

`mysql_secure_installation`


* Now create the Zabbix Database (zabbix_db) and database user (zabbix_user) and grant all privileges to the user on the Zabbix database.

```
mysql -u root -p
create database zabbix_db;
grant all privileges on zabbix_db.* to zabbix_user@localhost identified by 'Welcome123';
flush privileges;
exit
```

* Now import the database Schema

```
[root@zabbix ~]# cd /usr/share/doc/zabbix-server-mysql-3.0.25/
[root@zabbix zabbix-server-mysql-3.0.25]# gunzip create.sql.gz
[root@zabbix zabbix-server-mysql-3.0.25]# mysql -u root -p zabbix_db < create.sql
Enter password:
[root@zabbix zabbix-server-mysql-3.0.25]#
```

###  5.Edit Zabbix Server Configuration file


```
[root@zabbix ~]# vi /etc/zabbix/zabbix_server.conf
DBHost=localhost
DBName=zabbix_db
DBUser=zabbix_user
DBPassword=Welcome123
Timeout=30
```

###  6.Configure PHP Setting


```
[root@zabbix ~]# vi /etc/php.ini
max_execution_time = 600
max_input_time = 600
memory_limit = 256M
post_max_size = 32M
upload_max_filesize = 16M
date.timezone = Asia/Ho_Chi_Minh
```

* Allow the ports in the Firewall

```
firewall-cmd --permanent --add-port=10050/tcp
firewall-cmd --permanent --add-port=10051/tcp
firewall-cmd --permanent --add-port=80/tcp
firewall-cmd --reload 
systemctl restart firewalld

```

* Set the below Selinux rule.

`setsebool -P httpd_can_connect_zabbix=1`


* Start the Zabbix and Web Server Service

```
systemctl start zabbix-server
systemctl enable zabbix-server


systemctl start httpd
systemctl enable httpd
```


* Check log zabbix server.

`tailf /var/log/zabbix/zabbix_server.log`













