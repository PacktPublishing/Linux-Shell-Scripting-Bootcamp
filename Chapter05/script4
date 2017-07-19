#!/bin/sh
#
# 5/16/2017
#
echo "script4 - Linux Scripting Book"

checktermsize()
{
 rc1=0                       # default is no error
 if [[ $LINES -lt $1 || $COLUMNS -lt $2 ]] ; then
  rc1=1                      # set return code
 fi
 return $rc1
}

rc=0                         # default is no error
checktermsize 40 90          # check to see if terminal is at least 40x90
rc=$?
if [ $rc -ne 0 ] ; then
 echo "Return code: $rc from checktermsize"
fi

exit $rc

