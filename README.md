# HHA504_mysql_vm_vs_managed

## Cloud & Region
- Cloud: GCP
- Region: Central US

## Overview
This project compares a self-managed MySQL instance running on a VM with a cloud-managed MySQL service, focusing on setup effort and operational difficulty.

## Reproduction Steps
1. Provision VM / Managed MySQL
2. Configure networking and users
3. Store credentials in `.env`
4. Run `vm_demo.py` and `managed_demo.py`

## Connection Strings
- mysql+pymysql://USER:PASS@HOST:PORT/DB

Secrets are stored locally using python-dotenv and never committed.

## Evidence
Screenshots are available under `/screenshots` 
