#!/bin/sh
#
# 6/26/2017
#
if [ $# -ne 1 ] ; then
 echo "Usage: script3 file"
 echo " Will determine if the file exists."
 exit 255
fi

if [ -f $1 ] ; then
 echo File $1 exists.
 exit 0
else
 echo File $1 does not exist.
 exit 1
fi

