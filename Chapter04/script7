#!/bin/sh
#
# Auto backs up the file given if it has changed
# Assumes the cbS command exists
# Checks that ../back exists
# Copies to specific USB directory
# Checks if filename.bak exists on startup, copy if it doesn't

echo "autobackup by Lewis 5/9/2017 A"
if [ $# -ne 3 ] ; then
 echo "Usage: autobackup filename USB-backup-dir delay"
 exit 255
fi

# Create back directory if it does not exist
if [ ! -d back ] ; then
 mkdir back
fi

FN=$1                        # filename to monitor
USBdir=$2                    # USB directory to copy to
DELAY=$3                     # how often to check

if [ ! -f $FN ] ; then       # if no filename abort
 echo "File: $FN does not exist."
 exit 5
fi

if [ ! -f $FN.bak ] ; then
 cp $FN $FN.bak
fi

filechanged=0
while [ 1 ]
do
 cmp $FN $FN.bak
 rc=$?
 if [ $rc -ne 0 ] ; then
  cp $FN back
  cp $FN $USBdir
  cd back
  cbS $FN
  cd ..
  cp $FN $FN.bak
  filechanged=1
 fi

 sleep $DELAY
done

