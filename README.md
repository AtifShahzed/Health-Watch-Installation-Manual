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
sudo apt-get install -y mongodb-org
```
### Set Selections
```
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

#### Install .NET SDK or .NET Runtime on Ubuntu
```
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
```
```
sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-6.0
```
```
sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-6.0
```
```
sudo apt-get install -y dotnet-runtime-6.0
```
