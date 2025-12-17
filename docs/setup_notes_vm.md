
 # VM MySQL Setup Notes

## Cloud Provider: GCP
## Region: us-central1-c 
## Total Duration: 40 minutes

### Step 1: VM Creation (5 min)
- Created e2-small (2 vCPUs, 2 GB Memory)
- Ubuntu 25.10 minimal
- Opened firewall: 22, 3306

### Step 2: MySQL Installation (10 min)
```bash
sudo apt update && sudo apt install mysql-server mysql-client -y

```

### Step 3: Configuration (20 min)
Edited /etc/mysql/mysql.conf.d/mysqld.cnf:
Change the bind address
```
bind-address = 0.0.0.0
```
Restart MySQL:
```
sudo systemctl restart mysql
```

Created user and database:
```sql
CREATE USER 'chinyere'@'%' IDENTIFIED BY 'password';
CREATE DATABASE chinyere;
GRANT ALL PRIVILEGES ON chinyere *.* TO 'class_user'@'%';
```

### Step 4: Testing (5 min)
- Connected from Google Shell
- Ran Python script successfully

### Issues Encountered:
1. Connection refused → Forgot to restart MySQL after config change and had to keep restarting SSH
2. Access denied → Had to update firewall rules

### Total Setup Time: ~ 40 minutes

