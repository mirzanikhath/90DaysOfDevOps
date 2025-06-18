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

# Creating a shell script for backups rotationally ( backup_with_rotation.sh )

      #!/bin/bash

      #script name : backup_with_rotation.sh
      #description: backup a specified drirectory, creates timestamped backups , and keep only the latest 3 backups .

      #check if the directory path is given 
      if [ -z "41" ]; then 
           echo "usage: $0 /path/to/directory"
           exit 1
      fi 

      SOURCE_DIR="$1"
      BACKUP_BASE="$SOURCE_DIR/backups"

      #create backup directory if it doesn't exist 
      mkdir -p "$BACKUP_BASE"

      #create timestamp 
      TIMESTAMP=$(date +"%y5m%d_%H%M%s")
      BACKUP-DIR="$BACKUP_BASE/backup_$TIMESTAMP"

      #copy the comtents into the new backup directory 
      cp -r "$SOURCE_DIR" "BACKUP_DIR"

      ECHO "backup created at: $BACKUP_DIR"

      #rotation: Keep only the 3 most recent backups 
      cd '$BACKUP_BASE" || exit
      BACKUP_COUNT=$(ls -d backup_* 2>/dev/null | wc -l)

      if [ "$BACKUP_BASE" -gt 3 ]; then 
           OLD_BACKUPS=$(ls -d backup_* | sort | head -n -3)
           echo "Deleting old backups :"
           for backup in $OLD_BACKUPS; do
               echo "removing $backup"
               rm -rf "$backup"
           done
      fi


To use this script the command is :
        
        [command : ./backup_with_rotation.sh /home/username/documents]

This will :
 - Backup /home/username/documents
 - Create backups like: /home/username/documents/backups/backup_20250618_141501
 - Keeps only latest 3 backups 


To make this above script executable 

             [command: chmod +x backup_with_rotation.sh]

