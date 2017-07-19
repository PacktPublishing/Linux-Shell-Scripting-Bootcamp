#!/bin/sh
# 6/5/2017
# Chapter 8 - Script 1

URL=http://www.arlut.utexas.edu/omg/weather.html
FN=weather.html
TF=temp1.txt                 # temp file
LF=logfile.txt               # log file

loop=1
while [ $loop -eq 1 ]
do
 rm $FN 2> /dev/null         # remove old file
 wget -o $LF $URL
 rc=$?
 if [ $rc -ne 0 ] ; then
  echo "wget returned code: $rc"
  echo "logfile:"
  cat $LF

  exit 200
 fi

 date
 grep "Lake Travis Level:" $FN > $TF
 cat $TF | cut  -d ' ' -f 12 --complement

 sleep 1h
done

exit 0

