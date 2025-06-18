# AUTOMATED BACKUP AND RECOVERY USING CRON TAB 

# Cron Tab : 
crontab (short for cron table) is a linux utility used to schedule tasks to run automatically at specified times and intervals . these tasks are commonly known as cron jobs . 

# Automated Backups :

This refers to setting up scheduled tasks that automatically creare backups of file , databases , or system data.

Example : Backup a directory daily at 2 AM 

Lets say we have to backup /home/user/documents to /backup/documents.

We can create a shell script called (backup.sh)

# backup.sh
      #!/bin/bash
      tar -czf /bckup/documents_$(date +\%F).tar.gz /home/user/documents
      0 2 * * * /path/to/backup.sh


To make it executable the same command we use :

        [command: chmod +x backup.sh]

Then schedule it with cron tab :
 
         [ command : crontab -e ]


The line {0 2 * * * /path/to/backup.sh} means  it runs the script every day at 2:00 AM .

# backup Recovery 

Backup recovery is the process of restoring data from a backup after data loss or system failure .

While recovery itself is often manual ( to avoid accidental overwrites), we can automate parts of recovery like:

- Copying latest backup to restore directory 
- Reinitializing services or database with backup data.

Example of backup recovery :

Suppose we want to copy the latest backup into recovery folder every sunday at midnight :

       #!/bin/bash 
       latest=$(ls -t /backup/documents_*.tar.gz | head -1)
       mkdir -p /recovery.sh
       tar -xzf "$latest" -C /recovery.sh 
       0 0 * * 0 /path/to/recovery.sh

This runs every sunday and create the recovery of backups at 12:00 AM . 