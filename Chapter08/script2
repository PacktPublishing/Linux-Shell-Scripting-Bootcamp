#!/bin/sh
# 6/6/2017
# Chapter 8 - Script 2

URL="https://www.google.com/finance?cid=983582"
FN=outfile1.txt              # output file
TF=temp1.txt                 # temp file for grep

loop=1
while [ $loop -eq 1 ]
do
 rm $FN 2> /dev/null         # remove old file
 curl -o $FN $URL            # output to file
 rc=$?
 if [ $rc -ne 0 ] ; then
  echo "curl returned code: $rc"
  echo "outfile:"
  cat $FN

  exit 200
 fi

 echo ""                     # carriage return
 date
 grep "ref_983582_l" $FN > $TF
 echo -n "DJIA: "
 cat $TF | cut -c 25-33

 sleep 1h
done

exit 0

