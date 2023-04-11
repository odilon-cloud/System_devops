# CONTENT

1.write a shell script that will grab all files on the remote server and zip them in order to copy them on the local machine that is remoting them on the local server. The copy should unzipped upon being delivered.

2.Write a script to create 10 users at once and note of the 
following:
-created users should be assigned passwords right away
-created users should be forced to change passwords at their first login
-created users's accounts should be set to expire 30th March 2022

output 

3.Write a script to check on the remaining space on your root partition.
if used space is 20% used, you should send automatic email and an sms
to the system admin alerting him on the used space in order to take an action.

4..Write a script to backup daily work that is daily stored in users homedirectories
these files should be zipped and sent to your NAS locally hosted in your company.

5.Write a script that will take two files and compare them
if there is a change in one file it syncs with the original
file to match what has been added.

6.Write a script that will be sending a reminder email subject "reminder" content
"Dear user, please remember to do your assignment in order to develop muscles" 
to be sent to user1-user5 including yourname@gmail.com every day @8:00am

# to schedule scripts 
use 
``` bash
crontab -e 0 8 * * * /path/to/script.sh
```
the /path/to/script.sh is the script absolute path

the numbers are hours to be set
``` bash
.---------------- minute (0 - 59) 
|  .------------- hour (0 - 23)
|  |  .---------- day of month (1 - 31)
|  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ... 
|  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7)  OR sun,mon,tue,wed,thu,fri,sat 
|  |  |  |  |
*  *  *  *  *  command to be executed
```
