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

## 'Client does not support authentication protocol requested by server' error
- Start MySQL with `sudo mysql -u root -p`
- Enter your password
- Execute this query: `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';`
Where `root` is the user, `localhost` as the URL and `password` is the user's password
- Run `flush privileges;` to refresh privileges 
- Try connecting again. If failed, try without `@'localhost'` part.
