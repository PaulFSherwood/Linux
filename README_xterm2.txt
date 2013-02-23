http://www.thegeekstuff.com/2008/09/bash-shell-ps1-10-examples-to-make-your-linux-prompt-like-angelina-jolie/




8. Create your own prompt using the available codes for PS1 variable

Use the following codes and create your own personal PS1 Linux prompt that is functional and suites your taste. Which code from this list will be very helpful for daily use? Leave your comment and let me know what PS1 code you've used for your Linux prompt.

\a an ASCII bell character (07)
\d the date in "Weekday Month Date" format (e.g., "Tue May 26")
\D{format} - the format is passed to strftime(3) and the result is inserted into the prompt string; an empty format results in a locale-specific time representation. The braces are required
\e an ASCII escape character (033)
\h the hostname up to the first part
\H the hostname
\j the number of jobs currently managed by the shell
\l the basename of the shell's terminal device name
\n newline
\r carriage return
\s the name of the shell, the basename of $0 (the portion following the final slash)
\t the current time in 24-hour HH:MM:SS format
\T the current time in 12-hour HH:MM:SS format
\@ the current time in 12-hour am/pm format
\A the current time in 24-hour HH:MM format
\u the username of the current user
\v the version of bash (e.g., 2.00)
\V the release of bash, version + patch level (e.g., 2.00.0)
\w the current working directory, with $HOME abbreviated with a tilde
\W the basename of the current working directory, with $HOME abbreviated with a tilde
\! the history number of this command
\# the command number of this command
\$ if the effective UID is 0, a #, otherwise a $
\nnn the character corresponding to the octal number nnn
\\ a backslash
\[ begin a sequence of non-printing characters, which could be used to embed a terminal control sequence into the prompt
\] end a sequence of non-printing character






10. Use shell script inside PS1 variable

You can also invoke a shell script inside the PS1 variable. In the example below, the ~/bin/totalfilesize.sh, which calculates the total filesize of the current directory, is invoked inside the PS1 variable.
ramesh@dev-db ~> cat ~/bin/totalfilesize.sh

# 
# for filesize in $(ls -l . | grep "^-" | awk '{print $5}')
# do
#   let totalsize=$totalsize+$filesize
# done
# echo -n "$totalsize"
# 

ramesh@dev-db ~> export PATH=$PATH:~/bin
ramesh@dev-db ~> export PS1="\u@\h [\$(totalfilesize.sh) bytes]> "
ramesh@dev-db [534 bytes]> cd /etc/mail
ramesh@dev-db [167997 bytes]>
[Note: This executes the totalfilesize.sh to display the total
       file size of the current directory in the PS1 prompt]