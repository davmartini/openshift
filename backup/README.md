# Backup and Restore procedure

## Backup

### 1. Start a debug session for a control plane node
````
oc debug node/<node_name>
````

### 2. Change your root directory to the host
````
chroot /host
````

### 3. Run the cluster-backup.sh script and pass in the location to save the backup to.
````
/usr/local/bin/cluster-backup.sh /home/core/assets/backup
````
