#!/bin/sh
#
# 5/27/2017
#
echo "Chapter 5 - Script 6"

rc=0                         # return code
while [ $rc -eq 0 ]
do
 read -p "Enter value or q to quit: " var
 echo "var: $var"
 if [ "$var" = "q" ] ; then
  rc=1
 fi
done

rc=0                         # return code
while [ $rc -eq 0 ]
do
 read -p "Password: " -s var
 echo ""                     # carriage return
 echo "var: $var"
 if [ "$var" = "q" ] ; then
  rc=1
 fi
done

echo "Press some keys and q to quit."
rc=0                         # return code
while [ $rc -eq 0 ]
do
 read -n 1 -s var            # wait for 1 char, does not output it
 echo $var                   # output it here
 if [ "$var" = "q" ] ; then
  rc=1
 fi
done

exit $rc

