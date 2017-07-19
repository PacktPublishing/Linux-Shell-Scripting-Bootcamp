#!/bin/sh
#
# 5/16/2017
# Chapter 5 - Script 2
#
linecnt=1                    # line counter
loop=0                       # loop control var
while [ $loop -eq 0 ]
do
 echo "$linecnt  $RANDOM"    # display next random number
 let linecnt++
 if [ $linecnt -eq $LINES ] ; then
  linecnt=1
  echo -n "Press Enter to continue or q to quit: "
  read str                   # pause
  if [ "$str" = "q" ] ; then
   loop=1                    # end the loop
  fi
 fi
done

echo "End of script2"
exit 0

