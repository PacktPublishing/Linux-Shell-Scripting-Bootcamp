#!/bin/sh
#
# 6/2/2017
#
echo "Chapter 7 - Script 2"

FN=filenum1.txt              # input/output filename
MAXFILES=5                   # maximum number before going back to 1

if [ ! -f $FN ] ; then
  echo 1 > $FN               # create the file if it does not exist
fi

echo -n "Contents of $FN: "
cat $FN                      # display the contents

count=`cat $FN`              # put the output of cat into variable count
echo "Initial value of count from $FN: $count"

let count++
if [ $count -gt $MAXFILES ] ; then
 count=1
fi

echo "New value of count: $count"
echo $count > $FN

echo -n "New contents of $FN: "
cat $FN

echo "End of script2"
exit 0

