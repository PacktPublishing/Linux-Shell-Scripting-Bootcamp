#!/bin/sh
#
# 5/23/2017
#
echo "script3 - Linux Scripting Book"
FN=/tmp/log1.txt             # log file
while [ true ]
do
  echo Pinging $PROVIDER
  ping -c 1 $PROVIDER
  rc=$?
  if [ $rc -ne 0 ] ; then
    echo Cannot ping $PROVIDER
    date >> $FN
    echo Cannot ping $PROVIDER >> $FN
  fi
  sleep 60
done
echo "End of script3"        # 60 seconds
exit 0

