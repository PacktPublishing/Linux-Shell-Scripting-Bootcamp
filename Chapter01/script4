#!/bin/sh
#
# 6/13/2017
#
if [ $# -ne 1 ] ; then
 echo "Usage: script4 filename"
 echo " Will show various attributes of the file given."
 exit 255
fi

echo -n "$1 "                # Stay on the line

if [ ! -e $1 ] ; then
 echo does not exist.
 exit 1                      # Exit now if file does not exist
fi

if [ -f $1 ] ; then
 echo is a file.
elif [ -d $1 ] ; then
 echo is a directory.
fi

if [ -x $1 ] ; then
 echo Is executable.
fi

if [ -r $1 ] ; then
 echo Is readable.
else
 echo Is not readable.
fi

if [ -w $1 ] ; then
 echo Is writable.
fi

if [ -s $1 ] ; then
 echo Is not empty.
else
 echo Is empty.
fi

exit 0                       # No error

