#!/bin/sh
#
# 5/23/2017
#
echo "Chapter 6 - Script 4"
numusers=`who | wc -l`
while [ true ]
do
  currusers=`who | wc -l`           # get current number of users
  if [ $currusers -gt $numusers ] ; then
    echo "Someone new has logged on!!!!!!!!!!!"
    date
    who
#   beep
    numusers=$currusers
  elif [ $currusers -lt $numusers ] ; then
    echo "Someone logged off."
    date
    numusers=$currusers
  fi
  sleep 1                    # sleep 1 second
done

