#!/bin/sh
#
# 6/8/2017
#
echo "Chapter 9 - Script 8"
TTY=/dev/pts/35              # TTY of other terminal

# Subroutines
p1()                         # display to TTY
{
 rc1=0                       # default is no error
 if [ $# -ne 1 ] ; then
  rc1=2                      # missing parameter
 else
  echo "$1" > $TTY
  rc1=$?                     # set error status of echo command
 fi

 return $rc1
}

# Code
p1                           # missing parameter
echo $?

p1 Hello
echo $?

p1 "Linux Rules!"
echo $?

p1 "Programming is fun!"
echo $?

echo "End of script8"
exit 0

