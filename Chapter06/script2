#!/bin/sh
#
# 5/23/2017
#
echo "script2 - Linux Scripting Book"
while [ true ]
do
 # Run at 3 am
 date | grep -q 03:00:
 rc=$?
 if [ $rc -eq 0 ] ; then
  echo "Run commands here."
  date
  dt
 fi
 sleep 59                    # sleep 59 seconds
done
echo "End of script2"
exit 0

