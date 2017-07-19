#!/bin/sh
#
# 6/8/2017
#
set +x                       # turn debugging off

echo "Chapter 9 - Script 7"

x=0
for fn in *.txt
do
 echo "x: $x - fn: $fn"
 array[$x]="$fn"
 let x++
done

maxx=$x
echo "Number of files: $maxx"

set -x                       # turn debugging on

x=0
while [ $x -lt $maxx ]
do
  echo "File: ${array[$x]}"
  let x++
done

set +x                       # turn debugging off

echo "End of script7"
exit 0

