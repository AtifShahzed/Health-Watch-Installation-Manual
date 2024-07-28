# How To Install Nginx(Web Server) on Ubuntu
```
sudo apt update
sudo apt install nginx
```
```
sudo ufw app list
```
```
sudo ufw allow 'Nginx HTTP'
```
```
systemctl status nginx
```
 

# How To Install MongoDB  on Ubuntu

### Import the public key used by the package management system
```
sudo apt-get install gnupg curl
```
**To import the MongoDB public GPG key, run the following command:**
```
curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
```
### Create a list file for MongoDB
```
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```
### Reload local package database
```
sudo apt-get update
```
### Install the MongoDB packages
```
sudo apt-get install -y mongodb-org=7.0.12 mongodb-org-database=7.0.12 mongodb-org-server=7.0.12 mongodb-mongosh=7.0.12 mongodb-org-mongos=7.0.12 mongodb-org-tools=7.0.12


echo "mongodb-org hold" | sudo dpkg --set-selections
echo "mongodb-org-database hold" | sudo dpkg --set-selections
echo "mongodb-org-server hold" | sudo dpkg --set-selections
echo "mongodb-mongosh hold" | sudo dpkg --set-selections
echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
echo "mongodb-org-tools hold" | sudo dpkg --set-selections
```

## Run MongoDB Community Edition
```
ps --no-headers -o comm 1
```
#### Start MongoDB.
```
sudo systemctl start mongod
```
```
sudo systemctl daemon-reload
```
```
sudo systemctl status mongod
```
```
sudo systemctl enable mongod
```
```
sudo systemctl stop mongod
```
```
sudo systemctl restart mongod
```
