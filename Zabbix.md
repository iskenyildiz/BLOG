# Monitoring systems with Zabbix

`
sudo apt install update
`

Install Zabbix and its dependencies.

```
sudo apt-get install apache2 libapache2-mod-php 

sudo apt-get install mysql-server 

sudo apt-get install php php-mbstring php-gd php-xml php-bcmath php-ldap php-mysql
```

Add your local timezone to the file.

`
 sudo nano /etc/php/7.0/apache2/php.ini
 `
 Inside the file add
 
 ```
 [Date]
; http://php.net/date.timezone 
date.timezone = 'Europe/Istanbul'
```

`
wget http://repo.zabbix.com/zabbix/3.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_3.4-1+bionic_all.deb
`

`
sudo dpkg -i zabbix-release_3.4-1+xenial_all.deb
`

Update again.

`
sudo apt-get update
`

Install Zabbix Server

`
sudo apt-get install zabbix-server-mysql zabbix-frontend-php
`

```
mysql -u root -p

mysql> CREATE DATABASE zabbixdb;

mysql> GRANT ALL on zabbixdb.* to zabbix@localhost IDENTIFIED BY 'password';

mysql> FLUSH PRIVILEGES;
```

Load the Zabbix database schema to the database created above.

`
cd /usr/share/doc/zabbix-server-mysql
`

`
zcat create.sql.gz | mysql -u root -p zabbixdb
`

Edit the configuration file.

`
sudo nano /etc/zabbix/zabbix_server.conf
`

Change the stuff below for zabbix server to connect to the database.

```
 DBHost=localhost
 DBName=zabbixdb
 DBUser=zabbix  
 DBPassword=password
```

Restart Apache and Zabbix.

```
sudo service apache2 restart
sudo service zabbix-server restart
```

Go to ` http://yourzabbixserverIP/zabbix/` 

[![setup1-768x460.jpg](https://i.postimg.cc/zv4KgTc2/setup1-768x460.jpg)](https://postimg.cc/rRCD6Rc5)


[![setup2-768x475.jpg](https://i.postimg.cc/PqLLmC1B/setup2-768x475.jpg)](https://postimg.cc/DWTyhyjg)


## DB connection

[![setup3-768x474.jpg](https://i.postimg.cc/pdDvbxvm/setup3-768x474.jpg)](https://postimg.cc/R3VyKkNm)


[![setup4.jpg](https://i.postimg.cc/RFXj4ZDZ/setup4.jpg)](https://postimg.cc/Kk395xb6)

[![setup5.jpg](https://i.postimg.cc/jjT9ffVj/setup5.jpg)](https://postimg.cc/BjhM9XnW)

http://server_login_ip/zabbix/index.php 

[![login.jpg](https://i.postimg.cc/s1FKrFs2/login.jpg)](https://postimg.cc/4H5p6SKC)

# Zabbix Agent

`
sudo apt update
`

`
wget http://repo.zabbix.com/zabbix/3.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_3.4-1%2Bbionic_all.deb
`

`
sudo dpkg -i zabbix-release_3.4-1+xenial_all.deb
`

`
sudo apt install zabbix-agent
`

`
sudo nano /etc/zabbix/zabbix_agentd.conf
`

Inside the file

`
Server=Zabbix_Server_IP
Hostname=your_hostname
`

`
sudo systemctl restart zabbix-agent
`

`
sudo systemctl enable zabbix-agent
`
# Adding Hosts and Monitoring

[![dashbord.jpg](https://i.postimg.cc/KcdR2cSN/dashbord.jpg)](https://postimg.cc/9zYWPhfR)

[![host1-1-768x288.jpg](https://i.postimg.cc/VLQLh7nZ/host1-1-768x288.jpg)](https://postimg.cc/0rnsM0t7)

[![host3-1-768x313.jpg](https://i.postimg.cc/wTQHG963/host3-1-768x313.jpg)](https://postimg.cc/4myrKkHT)

[![host4-1-768x446.jpg](https://i.postimg.cc/25MfZ6x9/host4-1-768x446.jpg)](https://postimg.cc/WDGKRsC0)

[![host5-1-768x370.jpg](https://i.postimg.cc/hvn6L7Qs/host5-1-768x370.jpg)](https://postimg.cc/YGXdk03L)

[![host7-1-768x92.jpg](https://i.postimg.cc/LsZbGVzv/host7-1-768x92.jpg)](https://postimg.cc/5HbgCLKF)

## Make sure you have ports 10050 and 10051 allowed on all systems!
