#!/bin/sh
#
# 5/1/2017
#
echo "script4 - Linux Scripting Book"

if [ $# -ne 4 ] ; then
 echo "Usage: script4 number1 number2 number3 number4"
 echo "       Please enter 4 numbers."

 exit 255
fi

echo Parameters: $1 $2 $3 $4

echo Showing logical AND
if [[ $1 -eq $2 && $3 -eq $4 ]] ; then      # logical AND
 echo Clause 1
else
 echo Clause 2
fi

echo Showing logical OR
if [[ $1 -eq $2 || $3 -eq $4 ]] ; then      # logical OR
 echo Clause 1
else
 echo Clause 2
fi

echo "End of script4"
exit 0

