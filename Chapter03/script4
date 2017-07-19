#!/bin/sh
#
# 5/2/2017
#
echo "script4 - Linux Scripting Book"

if [ $# -ne 1 ] ; then
 echo "Usage: script4 string"
 echo "Will display the string on every line."
 exit 255
fi

tput clear                   # clear the screen

x=1
while [ $x -le $LINES ]
do
 echo "********** $1 **********"
 let x++
done

exit 0

