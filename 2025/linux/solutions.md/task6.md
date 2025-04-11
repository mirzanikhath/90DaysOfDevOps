# AUTOMATE BACKUPS WITH  SHELL SCRIPTING 

In general , shell scripts configure which directories to backups, and passes those directories as arguments to tar utility, which creates an archive file.the archived file can be moved or copied to another location, or can be created remotely on the remote file system or network file system(NFS).

The tar utility creates one archive file out of many files or directories. tar can also filter the files through compression utilities, thus reducing the size of the archive file.

!/bin/bash
####################################
#
# Backup to NFS mount script.
#
####################################
    
# What to backup. 
backup_files="/home /var/spool/mail /etc /root /boot /opt"
    
# Where to backup to.
dest="/mnt/backup"
    
# Create archive filename.
day=$(date +%A)
hostname=$(hostname -s)
archive_file="$hostname-$day.tgz"
    
# Print start status message.
echo "Backing up $backup_files to $dest/$archive_file"
date
echo
    
# Backup the files using tar.
tar czf $dest/$archive_file $backup_files
# Print end status message.
echo
echo "Backup finished"
date
    
 # Long listing of files in $dest to check file sizes.
ls -lh $dest

whenever we start to write the shell scripts we should start it with #!/bash/bin. we can use simple text editor or command line editor in order to create or edit the bash file . we use vim editor to create or edit the bash file.
the name of our backup file will be backup_scripts.sh . the .sh extension should be present at the end of the bash file.

#! /bin/bash # First Line of bash script

BackupTime = `date +%b-%d-%y` #get the current date

#Create a backup file using current date.

Destination = /home/usr/path/backup-$BackupTime.tar.gz

#The folder that contains the files that we want to backup

Source = /home/usr/path/folder

tar –cpzf $Destination $Source #Create the backup.

The important command here is the following:

tar –cpzf $Destination $Source

But what about -cpzf parameter?

c: create.

p: preserve permissions for the new files.

z: compress the files in order to reduce the size.

f: use archive file or device ARCHIVE.

Schedule your backup task:

for scheduling the backup task we use cron tab for that .
let us understand the crontab format:

minute (0–59) hour (0–23) day (1–31) month (1–12) weekday (0–6) command.

*****

the first (*) stands for every minute, the second (*) stands for every hour, the third (*) stands for every day , the fourth (*) stands for every month, the fifth (*) stands for every weekday . 