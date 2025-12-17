# Managed MySQL Setup Notes

## Cloud Provider: [GCP]
## Service: [Cloud SQL for MySQL]
## Region: [e.g., us-east1]
## Total time: ~20 minutes


## Step 1: Create Managed MySQL Instance (3-5 min)
1. Navigated to Cloud SQL in GCP Console
2. Clicked "Create Instance" → Selected MySQL
3. Configured instance:
   - **Instance ID**: `mysql-managed-demo`
   - **MySQL Version**: MySQL 8.0
   - **Password**: [Set strong root password - stored in .env]
   - **Region**: us-east1 (South Carolina)
   - **Zone**: us-east1-b (or Automatic)
   - **Machine Type**: Lightweight / db-n1-standard-1 (1 vCPU, 3.75 GB RAM)
   - **Storage**: 10 GB SSD (auto-expand enabled)
   - **High Availability**: Disabled (for cost savings in demo)
   - **Automated Backups**: Enabled (default, 7-day retention)

   ### None Required for GCP Cloud SQL!
This is one of the major benefits of managed MySQL on GCP - no manual configuration files to edit:
- No `/etc/mysql/mysql.conf.d/mysqld.cnf` to modify
- No bind-address to change
- No firewall rules to configure on the OS
- No systemctl commands needed