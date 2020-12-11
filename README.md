# Introduction

Sample yamls to take backup of OpenShift cluster running on Power and upload to IBM Cloud Object Storage (COS).
This is meant for demonstration and should not be used as-is for production.

This is based on work done by [Richard](https://www.richardwalker.dev/author/richard-walker.html) and mentioned in the 
following [link](https://www.richardwalker.dev/ocp-45-rough-etcd-backup-cronjob.html)

## Working
There are two cronjobs
1. backup-cronjob: Backup OpenShift cluster configuration every 30 minutes and keeps the backup in NFS persistent volume
2. upload-cronjob: Upload the backup from NFS persistent volume to IBM Cloud Object Storage every 40 minutes and deletes the backup from the NFS persistent volume

## Deploy

1. Update `cos-creds.yaml` with your IBM CLOUD API key
2. Update `backup-pv.yaml` with details of the NFS server
3. Update `upload-cronjob.yaml` with COS and Cluster proxy details

