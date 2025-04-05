# LOG FILE ANALYSIS
log file analysis is the process of reviewing , interpreting computer generated codes (logs) to understand deeply about system security ,performance and helping in errors ,patterns etc...

log files are the record of events ,actions and errors that occurs in the system or application.they contains information on what happened , when happened and who is involved in the change of system logs .logs data can be structured semi-structured or unstructured.

IMPORTANCE OF LOG FILES 

1. Troubleshooting:Log files can help pinpoint the root cause of issues, errors, or crashes. 
2. Performance Monitoring:They provide insights into system performance, identify bottlenecks, and optimize resource usage. 
3. Security: Log analysis can detect suspicious activity, identify security breaches, and help prevent future attacks. 


# GREP,AWK AND SED IN LOG ANALYSIS 

GREP ,SED and AWK are the standard utility tools of linux that are able to process text in the file. GREP search the pattern of the files in log system while SED command edits the file without actual going inside that file and whereas AWK command is slitghtly different from both the commands it can find the information when the tasks were completed on what time and many more information of the logs in the system logs .AWK is a fully fledghed programming language which also does the arithematic operations or performs the comparision on the text inside the extracted file .

GREP (Global Regular Expression Pattern)

GREP is a good tool used to search the pattern of text inside the file .this GREP command helps in searching the pattern of text inside the text file .

              syntax: grep [options] pattern [file]

for example if we have to search errorlogs in the apache log file we used grep here :
               
               command:grep "ErrorLog" /etc/apache2/apache2.conf

GREP is able to find the configuration of ErrorLogs in the Apache log file .In the linux distribution the GREP configuration is found in red colour . 

we can invert the pattern by using -v with the command :
               
               command : grep -v "INFO" log.txt

in the above command as we used -v it prints only the lines which does contains "INFO" in log.txt file.

grep commands also can be used to print preceeding and succeeding lines from a particular file :

                   command : grep -A 5 ERROR log.txt

this -A is used to print the preceeding 5 lines of ERROR in log.txt.


                    command : grep -B 5 ERROR log.txt.


this -B is used to print the succeeding 5 lines of ERROR log.txt.

                    command : grep -C 5 ERROR log.txt

this -C is used to print both preceeding and succeeding 5 lines of ERROR in log.txt


SED(stream editor ):

the SED command is the stream editor which edits the stream of the characters. it the mkkmost powerful tool that GREP as it edits the word inside the file without actually opening it . 

             syntax : sed [options] scripts.sh

here , in options we can put the words which we want to edit without actually going inside scripts.sh 

we can use SED command as GREP also like 

               command : sed -n '/ERROR/ p' log.txt

we can use SED command for substituting the matched string with its replacement :

                command : sed 's/pattern/replacement/'

this command edits wherever we have pattern it substitues replacement in that place .

                example: sed 's/ERROR/critical/' log.txt

SED command also modifies the file to which we have to make changes by using -i it creates the backup file for that particular file to which we have to apply changes .

                example : sed -ibackup 's/pattern/replacement/' log.txt

when we run the above command automatically the backup file for log.txt will be created with the changes we want . 

SED command also can be restricted to the specific line number like 

                example : sed '3 s/ERROR/critical/' log.txt

the above command SED will operate only on the line number 3 in the log.txt file.

we can also give the range of lines to which SED  should operate 

                  example : sed '3,5 s/ERROR/critical/' log.txt

when we run the above command the sed will operate only on those lines between line number 3 and 5.

AWK (Aho, Weinberger, and Kernighan):

awk word came from its designers .it is a fully fledghed programming language. it not only offers multitude of built-in functions as scripts,arthematic and time manipulation but also allows user to define its own functions as a regular scripting language .

                 syntax: awk [options] scripts file 

in which we give pattern and actions to be applied on that pattern . if pattern is absent then the actions will be applied to all the lines present in the file .

we can replicate AWK with GREP also like:

                command : awk '/ERROR/{print $0}' log.txt

AWK command also applies the header and footer to the scripts inside the log file :

                  example: awk 'BEGIN {print"LOG SUMMARY \n....................."} {print} END{print"...................\nEND  OF LOG SUMMARY"}' log.txt

AWK command also helps in column manipulation means it will give us only the columns which we mention in the command 
                     
                     command : awk '{print $1 $3}' log.txt 

the above command will print only column 1 and 3 from log.txt file 

AWK command also helps us in finding the logs between the particular time intervals 

                       command : awk 'if($1 >19:00:00 ) && ($1<19:15:00) /ERROR/ {print $1}' log.txt

this command will print all the logs in between 19:00:00 and 19:15:00 so we can easily find out how many ERROR logs are present the particular time interval .

AWK command helps us in finding particular number of logs in the log.txt file .

                        command : awk 'if ($1>153578987) {print $0}' log.txt 

the above commands gives us the logs of only those numbers which comes after  153578987 number of log . 

Q1 Download the log file from the repository.
ans : downloaded the log file from the URL : https://github.com/logpai/loghub/blob/master/Linux/Linux_2k.log

Q2 Use grep to find all occurrences of the word "error".
ans : found all the occurences of the word "error" from the log file 

                   command : grep "error" Linux_2k.log


Q3 Use awk to extract timestamps and log levels:
ans: to extract the log levels according to time 

                   command : awk '$3>="04:06:18" && $3<="04:12:43" {print $1 $2 $3 $6}' Linux_2k.log


Q4 Use sed to replace all IP addresses with [REDACTED] for security.
ans : to replace all IP addresses column with [REDACTED] command :

                  command : sed 's/$6/[REDACTED]/g' Linux_2k.log

            




