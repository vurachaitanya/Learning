Operation|Option|Example
---|---|---
Find a string in 1 or more files||grep 'string' filename1 filename2 ... filenamen
Case insensitive search|i|grep -i 'string' filename
Use regular expressions (regex)||grep 'regex' filename
Look for words|w|grep -w 'word' filename
Display n lines after matching string|A|grep -A n 'string' filename
Display n lines before matching string|B|grep -B n 'string' filename
Display n lines around matching string|C|grep -C n 'string' filename
Recursive grep|r|grep -r 'hackers-club.cn' /var/log/apache2/archives/
Return all lines which don't match the pattern|v|grep -v 'warning' /var/log/syslog
Use regex|e|grep -e 'string1' -e 'string2' filename
||grep --regexp 'string' filename
Return lines starting with 'al'||grep -e '^al' filename
Use extended regex|E|grep -E 'apache|wheel|root' filename
Get lines containing 1+ w||grep -E 'w+' filename
Get lines with 3 w in a row (www)||grep -E 'w{3}' filename
Get lines containing between 3 and 6 m in a row||"grep -E 'm{3|6}' filename"
Get lines containing jason or jackson||grep -E 'ja(s|cks)on' filename
Count results|c|grep -c 'error' /var/log/syslog
Display filename|l|grep -l 'string' /var/log/*
Only show the matching part of the string|o|grep -o 'string' filename
Show line number|n|grep -n 'string' filename
