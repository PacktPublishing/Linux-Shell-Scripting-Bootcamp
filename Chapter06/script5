#!/bin/sh
#
# 5/23/2017
#
echo "script5 - Linux Scripting Book"
FN=work1.zip
cd /tmp
mkdir work 2> /dev/null      # suppress message if directory already exists
cd work
cp /etc/motd .
cp /etc/issue .
ls -la /tmp > tmp.txt
ls -la /usr > usr.txt
rm $FN 2> /dev/null          # remove any previous file
zip $FN *
echo File "$FN" created.
# cp to an external drive, and/or scp to another computer
echo "End of script5"
exit 0

