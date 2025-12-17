# GCP Cloud SQL for MySQL (Managed)

## Create Cloud SQL Instance
1. Go to SQL → Create Instance
2. Choose MySQL
  Configure:

      Instance ID: `mysql-managed`

      MySQL version: 8.0.41

      Region: same as VM (us-central1)

      Machine type: Lightweight (1 vCPU, 628.74 MB)

      Storage: 10 GB
4. Make sure Public IP connectivity is enabled.


## Create Database and User
1. Go to Databases → Create database
    Name: `dummydb`
2. Go to Users → Create user
    Username: `class_user`
    Host: `%`(allow any host)
    Password: strongpassword

## Run Python Script
1. Update `.env`
2. Run `scripts/managed_demo.py`


## Notes
1. Automatic backups (enabled by default)
2. Patching handled by GCP
