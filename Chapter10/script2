#!/bin/sh
#
# 1/26/2014
#
# create a command script

if [ $# -eq 0 ] ; then
 echo "Usage: mkcmd command"
 echo " Copies mkcmd.template to command and edits it with kw"
 exit 255
fi

if [ -f $1 ] ; then
  echo File already exists!
  exit 2
fi

cp $BIN/mkcmd.template $1
kw $1

