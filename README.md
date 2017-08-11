# RTC-Work-Item-Creation-with-Email
Task 1 - Determine RTC APIS
Understanding and Using RTC client APIS - https://rsjazz.wordpress.com/2013/03/20/understanding-and-using-the-rtc-java-client-api/
Article on Workitem Creation, Refer Plain Java client section code - https://jazz.net/wiki/bin/view/Main/ProgrammaticWorkItemCreation

Task 2 - Get access to lotus notes id ex.BHThelp desk to drive project

Task 3 - Get familiarized with RTC work item tool
Here is information about RTC work item took tool to interact with RTC:

https://w3-connections.ibm.com/wikis/home?lang=en-us#!/wiki/Wc81535b497b4_4f3a_8250_45c558f66d91/page/rtcwicli

The RTC Work Item Command Line (rtcwi) is a command line interface for accessing the work item capabilities. 

It is used to get information from RTC and also has an option to create work items
It is written in python, it might be able to be modified for epics and stories.

Task 4 - Clenotes/Command line email client, clenotes is used to trigger the emails
https://github.com/OpenNTF/CommandLineEmailClient
Git Source for clenotes
https://www.openntf.org/main.nsf/project.xsp?r=project/command%20line%20email%20client/

This is the Windows download of the zip file ready for use on Windows. (also have a .sh for Linux use),

https://www.openntf.org/Projects%5Cpmt.nsf/downloadcounter?openagent&project=Command%20Line%20EMail%20Client&release=5.3.1&unid=8182CF6A71C72D15852580C80030F09C&attachment=clenotes-5.3.1.zip
(clenotes-5.3.1.zip)
syntax for running clenotes.cmd --help command
clenotes.cmd --help
Command Line Email Client for IBM Notes v5.3.1
Copyright (C) 2002, 2017 by IBM Corporation.
Licensed under the Apache License v2.0.

Usage: clenotes.cmd [global-options] [cmd [cmd-options]]

Global options (common for one or more commands):
 --adjust-day=ARG          Adjust cutoff day. Use integer value 
                           (1=mail today and yesterday, 2=mail from 
                           day before yesterday until today, and so 
                           on). No cutoff date means either "no 
                           cutoff date" or "today only" and it 
                           depends on command context.
 --all-mime-texts          Print all MIME text parts when reading 
                           emails. By default prints only the first 
                           mime text part, usually text/plain.
 --database-name=ARG       Name of the database to be opened.
 --delim=ARG               Custom delimiter when formatting mail with 
                           --output-format option. Default delimiter 
                           is ';'
 --dxl=ARG                 Exports mail as DXL. Optional value is 
                           file name where DXL is exported.
 --dxli=ARG                Import DXL as mail database to be used.
 --exec-time               Display elapsed time of the program 
                           execution. Does not include Java start-up 
                           time.
 --folder=ARG              Specify mail folder to be used. By default 
                           'All documents' is used. Requires folder 
                           references to be enabled.
 --help=ARG                List options and commands. Optional 
                           argument is command name to get help or 
                           "!" to list command names only.
 --local                   Use local mail database.
 --log                     Enable logging for current session. 
                           Deletes old log file and writes new.
 --loga                    Enable logging for current session. 
                           Appends to existing log file.
 --no-striphtmltags        Do not strip HTML tags when reading HTML 
                           emails.
 --noheader                Do not print header.
 --output-format=ARG       Custom output format string when listing 
                           emails. Formatting options: "d=Date", 
                           "t=time", "Z=timezone", "g=GMT time", 
                           "s=subject", "f=from", "I=from (inet 
                           address)", "m=mailer", "D=message id", 
                           "S=message size", "!=do not print index 
                           number", "a=list attachments". For 
                           example: --output-format=dts print email 
                           date, time and subject in one line.
 --password=ARG            Users Notes ID password
 --replica-id=ARG          Select local database by specifying 
                           replica ID of the local database. Use 
                           "maildbinfo" command to get replica ID of 
                           local mail database.
 --server-name=ARG         Domino server name where database is 
                           located.
 --tab                     Use tab as delimiter when using 
                           output-format option.
 --version                 Version info.

Commands:
 appointments              Show appointments.
   --desc                  Show appointment description.
   --optional              List optional participants.
   --required              List required participants.
   --sincedate=ARG         List appointments since specified date. 
                           Date format is "DD/MM/YYYY".
   --today                 List only todays appointments.
   --week                  List appointments in next 7 days.
 dev                       Command for development/experimentation.
   --disable               Disable folder references.
   --enable                Enable folder references.
   --folderrefs            Show status of folder references.
   --listfolders           List folders and their UNIDs.
   --putallinfolder        Put all documents in folders. Use after 
                           enabling folder references.
 list                      List all mail in mail database.
   --all                   List all documents, not only mails.
   --end=ARG               End index when listing mail.
   --folderview=ARG        Specify mail folder to be used. Used when 
                           folder is actually a view.
   --read=ARG              Read specific mail (given as index, or '*' 
                           for all mails) from result set. See also 
                           read-command options.
   --sortfield=ARG         Sort mails by field. Use values DATE, 
                           SUBJECT or FROM. Default is DATE.
   --sortorder=ARG         Sort mails. Use value ASC or DESC. Default 
                           is ASC
   --start=ARG             Start index when listing mail.
 maildbinfo                Mail database information. Use 
                           --server-name, --replica-id or 
                           --database-name to specify database other 
                           than mail database.
 notes-version             The release of Domino the session is 
                           running on.
 read                      Read latest mail or use with today, list 
                           or search commands
   --all                   Reply email to all recipients.
   --attachments           Print attachment file names in this mail 
                           document.
   --body=ARG              Body in reply mail.
   --delete                Delete mail.
   --detach-all            Detach all attachment to current 
                           directory.
   --detach-dir=ARG        Specify directory for detached 
                           attachments.
   --detach-file=ARG       Detach specified attachment to current 
                           directory or directory specified with 
                           --detach-dir option.
   --fields                Print all fields and their types in mail 
                           document.
   --fieldvalues=ARG       Print value(s) of given field.
   --linelen               Line length of mail to be read. Works only 
                           for Notes RichText mails.
   --move-to-folder=ARG    Move mail to specified folder.
   --no-body               Do not print mail body.
   --no-confirmation       Do not confirm mail delete.
   --replace               Replace attached file, if it already 
                           exists. By default, if file exists, a 
                           sequence number is appended to file name.
   --reply                 Reply email to sender.
   --source-folder=ARG     Source folder of mail to be moved. If not 
                           specified, default is "$Inbox".
 replicate                 Replicate local database to server.
   --database=ARG          Specify local database file path for 
                           replication. Default is mail database.
   --replica-id=ARG        Replica ID of database. Default is mail 
                           database replica ID.
   --server=ARG            Specify server for replication. Default is 
                           mail database server.
 search                    Search mail.
   --formula=ARG           Search mails using Notes formula.
   --formula-file=ARG      Search mails using Notes formula in 
                           specified file.
   --from=ARG              Search mails with sender address.
   --fulltext=ARG          Search mails using full text.
   --list                  List mail from result set. See also 
                           list-command options.
   --nocase                Use case-insensitive when searching by 
                           from or subject.
   --read=ARG              Read specific mail (given as index, or '*' 
                           for all mails) from result set. See also 
                           read-command options.
   --self                  Match also mails sent by self when 
                           searching by subject.
   --subject=ARG           Search mails with subject.
   --view=ARG              Search mails from specified View. Only 
                           --fulltext search is available and 
                           --adjust-day is ignored.
 send                      Send mail.
   --attach=ARG            Comma separated list of files to be 
                           attached.
   --bcc=ARG               Comma separated list of BCC recipients. 
                           For example: 
                           --bcc=="recp1@com,recp2@another.com"
   --body=ARG              Mail body.
   --cc=ARG                Comma separated list of CC recipients. For 
                           example: 
                           --cc=="recp1@com,recp2@another.com"
   --charset=ARG           Charset of --file-body file. Default is 
                           UTF-8.
   --encrypt               Encrypt mail.
   --file-bcc=ARG          Path to text file that includes comma 
                           separated list of BCC recipients.
   --file-body=ARG         Mail body read from specified text file.
   --file-cc=ARG           Path to text file that includes comma 
                           separated list of CC recipients.
   --file-signature=ARG    Add signature to email from specified 
                           file.
   --file-to=ARG           Path to text file that includes comma 
                           separated list of recipients.
   --html                  Send mail as HTML.
   --nosave                Do not save mail.
   --principal=ARG         Override email sender. Remember to add 
                           Notes domain after email, for example: 
                           sender@somewhere.com@NotesDomain.
   --replyto=ARG           Set reply-to parameter to email.
   --sign                  Sign mail.
   --signature=ARG         Add signature to email.
   --subject=ARG           Mail subject.
   --to=ARG                Comma separated list of recipients. For 
                           example: 
                           --to=="recp1@com,recp2@another.com"
   --urgent                Send mail as urgent.
 shell                     Command line email shell, like v1.0 in the 
                           old days.
 today                     List todays mail. Equivalent of using 
                           'clenotes --adjust-day=0 list' command.


Task 5 - Scripting,Cygwin and Command Line
You will need cygwin to write some functionality to acess the lotus notes email, windows command line will not evoke 
all necessary commands.
You will need to wrte scripts using the clenotes.cmd to get email list, parse and create property files.



Some useful links
1. https://jazz.net/wiki/bin/view/Main/WorkItemAPIsForOSLCCM20
2. https://rsjazz.wordpress.com/2013/03/14/what-apis-are-available-for-rtc-and-what-can-you-extend/
3. https://www.openntf.org/Projects%5Cpmt.nsf/downloadcounter?openagent&project=Command%20Line%20EMail%20Client&release=5.3.1&unid=8182CF6A71C72D15852580C80030F09C&attachment=clenotes-5.3.1.zip

