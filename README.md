# RDS (Relational Database Service) StudentApp Project
---

##  Frontend -
Node.js must be installed.

npm must be installed.

apache2 must be installed.

---

##  Backend -
Java Development Kit (JDK 17 or higher) must be installed.

Maven must be installed.

---

##  Database -
Install MariaDB.

---

##  Before starting, make sure:-

1. RDS (Relational Database Service) is created.

2. EC2 Instance is launched.
 
3. MySQL Client is installed.

---

##  Steps and Commands:
### 1. RDS (Realtional Database Service)

 Create RDS 

 Full configuration

 MariaDB

 Templates -- Sandbox

 Master username -- EX. (linux)

 Master password --  EX. (redhat123)

 VPC security group -- EX. (launch-wizard-1)

 Create Database

---

 ### 2. EC2 (Elastic Compute Cloud)

. Launch instance

. Instance type -- EX. (c7i.xlarge)

. Security groups -- EX. (launch-wizard-1)

. Storage -- EX. (20GB)

. Launch instance

---


### 3. Commands =

#### 1. Switch to root user
```sh
sudo -i
```


#### 2. Update the instance
```sh
apt update
```
#### 3. Install Mysql-client
```sh
apt install mysql-client -y
```
#### 4. Mysql-client Database 
```sh
mysql -h (endpoint) -u (username) -p
```
```sh
Enter password (password)
```
##### RDS Database Endpoint copy & paste
##### Example: mysql -h database-1.ca9eie2mihs7.us-east-1.rds.amazonaws.com -u linux -p
##### Example: redhat123

```sh
CREATE DATABASE student_db;
```
```sh
GRANT ALL PRIVILEGES ON springbackend.* TO 'username'@'localhost' IDENTIFIED BY 'password';
```
```sh
show databases;
```
```sh
exit;
```
#### 5. Clone the GitHub Repository
```sh
git clone <GitHub_Repository_Link>
```
##### Example: git clone https://github.com/username/student-registration.git

#### 6. Backend

```sh
cd <GitHub_Repository_Name>/backend
```
```sh
apt update
```
```sh
apt install openjdk-17-jdk -y
```
```sh
java -version
```
```sh
apt install maven -y
```
##### Write src/main/resources/application.properties file
```sh
nano src/main/resources/application.properties .
```
```sh
server.port=8080
spring.datasource.url=jdbc:mariadb://database-1.curkg4kao7cw.us-east-1.rds.amazonaws.com:3306/student_db
spring.datasource.username=linux
spring.datasource.password=redhat123
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```
```sh
mvn clean package
```
```sh
cd target/
```
```sh
java -jar student-registration-backend-0.0.1-SNAPSHOT.jar
```
#### 7. Frontend

##### Duplicate the tab

```sh
sudo -i
```
```sh
apt update
```
```sh
cd EasyCRUD/frontend/
```
```sh
apt update && apt install nodejs npm -y
```
```sh
npm install
```
##### Write env file
```sh
nano .env
```
```sh
VITE_API_URL = "http://(Paste publicIP):8080/api"
```
##### Ex. VITE_API_URL = "http://54.82.224.7:8080/api"
```sh
ls -a
```
```sh
npm run build
```
```sh
apt install apache2 -y
```
```sh
systemctl start apache2
```
```sh
cp -rf dist/* /var/www/html/
```

---
## GoTo New Tab & Paste (Instances PublicIP)
