 VM MySQL Setup Notes

## Cloud Provider: GCP
## Region: us-east1-b
## Total Duration: 40 minutes

### Step 1: VM Creation (5 min)
- Created e2-medium instance
- Ubuntu 22.04 LTS
- Opened firewall: 22, 3306

### Step 2: MySQL Installation (10 min)
```bash
sudo apt update && sudo apt install mysql-server -y
sudo systemctl enable mysql
```

### Step 3: Configuration (15 min)
Edited /etc/mysql/mysql.conf.d/mysqld.cnf:
```
bind-address = 0.0.0.0
```

Created user and database:
```sql
CREATE USER 'class_user'@'%' IDENTIFIED BY 'password';
CREATE DATABASE class_db_netid;
GRANT ALL PRIVILEGES ON class_db_netid.* TO 'class_user'@'%';
```

### Step 4: Testing (5 min)
- Connected from Google Shell
- Ran Python script successfully

### Issues Encountered:
1. Connection refused → Forgot to restart MySQL after config change and had to keep restarting SSH
2. Access denied → Had to update firewall rules

### Total Setup Time: ~ 40 minutes