# Setting Up MySQL on Fedora Linux

## Installing MySQL
The community provides a MySQL package in the main repo
```
sudo dnf install community-mysql-server
```

## Configuring MySQL 
Enable the service at boot and start:
```
sudo systemctl enable mysqld
sudo systemctl start mysqld
```

## Configure SQL before first use
```
sudo mysql_secure_installation
```
Some questions will be asked, feel free to answer _yes_ to all.


## Using SQL
```
sudo mysql -u root -p 
```
Enter the password when prompted.


## Removing SQL
sudo dnf remove community-mysql-server

