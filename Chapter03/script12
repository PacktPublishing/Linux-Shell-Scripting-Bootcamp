#!/bin/sh
#
# 5/3/2017
#
echo "script12 - Linux Scripting Book"

if [ $# -ne 1 ] ; then
 echo "Usage: script12 process-directory"
 echo " For example: script12 /proc/20686"
 exit 255
fi

FN=$1                        # process directory i.e. /proc/20686
rc=1
while [ $rc -eq 1 ]
do
 if [ ! -d $FN ] ; then      # if directory is not there
  echo "Process $FN is not running or has been terminated."
  let rc=0
 else
  sleep 1
 fi
done

echo "End of script12"
exit 0

